---
title: Entrenamiento de un modelo de regresión para predecir un valor mediante ML.NET
description: Descubra cómo entrenar un modelo de regresión de aprendizaje automático para predecir un valor mediante ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: e6cd62876f6ac9497e7485b93d4dbd8f95ccc1bb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156533"
---
# <a name="train-a-regression-model-to-predict-a-value-using-mlnet"></a>Entrenamiento de un modelo de regresión para predecir un valor mediante ML.NET

Por lo general, hay tres pasos para el entrenamiento del modelo en ML.NET:

1. Obtener los datos de entrenamiento en forma de un `IDataView`
2. Crear la “canalización de aprendizaje” como una secuencia de “operadores” de elementales (estimadores).
3. Llamar a `Fit` en la canalización para obtener el modelo entrenado.

En este [archivo de ejemplo](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv), la etiqueta predicha (`target`) es la última columna (12) y el resto son características:

```console
feature_0;feature_1;feature_2;feature_3;feature_4;feature_5;feature_6;feature_7;feature_8;feature_9;feature_10;target
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // We read the first 11 values as a single float vector.
        new TextLoader.Column("FeatureVector", DataKind.R4, 0, 10),

        // Separately, read the target variable.
        new TextLoader.Column("Target", DataKind.R4, 11),
    },
    // First line of the file is a header, not a data row.
    HasHeader = true,
    Separator = ";"
});

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var trainData = reader.Read(trainDataPath);

// Step two: define the learning pipeline.

// We 'start' the pipeline with the output of the reader.
var pipeline =
    // First 'normalize' the data (rescale to be
    // between -1 and 1 for all examples)
    mlContext.Transforms.Normalize("FeatureVector")
    // Add the SDCA regression trainer.
    .Append(mlContext.Regression.Trainers.StochasticDualCoordinateAscent(label: "Target", features: "FeatureVector"));

// Step three. Fit the pipeline to the training data.
var model = pipeline.Fit(trainData);
```