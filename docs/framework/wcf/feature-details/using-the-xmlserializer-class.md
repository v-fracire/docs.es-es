---
title: "Utilizaci&#243;n de la clase XmlSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XmlSerializer [WCF], uso"
ms.assetid: c680602d-39d3-44f1-bf22-8e6654ad5069
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Utilizaci&#243;n de la clase XmlSerializer
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puede utilizar dos tecnologías de serialización diferentes para convertir los datos de su aplicación en XML transmitidos entre los clientes y servicios, un proceso llamado serialización.  
  
## DataContractSerializer como predeterminado  
 De forma predeterminada [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la clase <xref:System.Runtime.Serialization.DataContractSerializer> para serializar los tipos de datos. Este serializador admite los tipos siguientes:  
  
-   Tipos primitivos \(por ejemplo, enteros, cadenas y matrices de bytes\), así como algunos tipos especiales, como <xref:System.Xml.XmlElement> y <xref:System.DateTime>, que se tratan como primitivos.  
  
-   Tipos de contrato de datos \(los tipos marcados con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> \).  
  
-   Los tipos marcados con el atributo <xref:System.SerializableAttribute>, incluidos los tipos que implementan la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Los tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>.  
  
-   Muchos tipos de colección comunes, que incluyen muchos tipos de colección genéricos.  
  
 Muchos tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se incluyen en las dos últimas categorías y son, de este modo, serializables. Las matrices de tipos serializables también son serializables. Para obtener una lista completa, vea [Especificación de transferencia de datos en contratos de servicio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>, utilizado junto con los tipos de contrato de datos, es la manera recomendada de escribir nuevos servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
## Cuándo utilizar la clase XmlSerializer  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también admite la clase <xref:System.Xml.Serialization.XmlSerializer>. La clase <xref:System.Xml.Serialization.XmlSerializer> es no es exclusiva de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Es el mismo motor de serialización que usan los servicios Web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. La clase <xref:System.Xml.Serialization.XmlSerializer> admite un conjunto mucho más estrecho de tipos que la clase <xref:System.Runtime.Serialization.DataContractSerializer>, pero permite mucho más control sobre el XML resultante y admite mucho más de la norma del lenguaje de definición de esquemas XML \(XSD\). Tampoco necesita ningún atributo declarativo en los tipos serializables.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] el tema Serialización XML en la documentación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. La clase <xref:System.Xml.Serialization.XmlSerializer> no admite tipos de contrato de datos.  
  
 Cuando se usa Svcutil.exe o la característica **Agregar referencia de servicio** en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] para generar el código de cliente para un servicio de otro fabricante o para tener acceso a un esquema de otro fabricante, se selecciona automáticamente un serializador adecuado. Si el esquema no es compatible con <xref:System.Runtime.Serialization.DataContractSerializer>, se selecciona el <xref:System.Xml.Serialization.XmlSerializer>.  
  
## Intercambio manual a XmlSerializer  
 En algunas ocasiones, puede ser necesario intercambiar manualmente a <xref:System.Xml.Serialization.XmlSerializer>. Esto sucede, por ejemplo, en los casos siguientes:  
  
-   Al migrar una aplicación desde los servicios Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], usted puede querer reutilizar los tipos compatibles existentes, <xref:System.Xml.Serialization.XmlSerializer>\- en lugar de crear nuevos tipos de contrato de datos.  
  
-   Cuando es importante el control preciso sobre el XML que aparece en los mensajes, pero no hay disponible un documento de lenguaje de descripción de servicios Web \(WSDL\), por ejemplo, al crear un servicio con tipos que tienen que cumplir un cierto esquema normalizado, publicado, no compatible con DataContractSerializer.  
  
-   Al crear servicios que siguen la norma de Codificación SOAP heredada.  
  
 En éstos y otros casos, puede intercambiar manualmente a la clase <xref:System.Xml.Serialization.XmlSerializer> aplicando el atributo `XmlSerializerFormatAttribute` a su servicio, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[c_XmlSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#1)]
 [!code-vb[c_XmlSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#1)]  
  
## Consideraciones de seguridad  
  
> [!NOTE]
>  Es importante tener el cuidado al intercambiar los motores de serialización. El mismo tipo puede serializar de maneras diferentes, dependiendo del serializador que se utiliza. Si por error utiliza un serializador erróneo, podría estar divulgando información de un tipo que no tenía intención de divulgar.  
  
 Por ejemplo, la clase <xref:System.Runtime.Serialization.DataContractSerializer> sólo serializa los miembros marcados con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> al serializar los tipos de contrato de datos. La clase <xref:System.Xml.Serialization.XmlSerializer> serializa cualquier miembro público. Vea el tipo del código siguiente.  
  
 [!code-csharp[c_XmlSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#2)]
 [!code-vb[c_XmlSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#2)]  
  
 Si el tipo se utiliza inadvertidamente en un contrato de servicios donde está seleccionada la clase <xref:System.Xml.Serialization.XmlSerializer>, se serializa el miembro `creditCardNumber` que probablemente no corresponde.  
  
 Aunque la clase <xref:System.Runtime.Serialization.DataContractSerializer> es el valor predeterminado, puede seleccionarlo explícitamente para su servicio \(aunque esto no se debería exigir nunca\) aplicando el atributo <xref:System.ServiceModel.DataContractFormatAttribute> al tipo de contrato de servicios.  
  
 El serializador utilizado para el servicio es una parte integrante del contrato y no se puede cambiar seleccionando un enlace diferente o cambiando otra configuración.  
  
 Otras consideraciones de seguridad importantes se aplican a la clase <xref:System.Xml.Serialization.XmlSerializer>. En primer lugar, se recomienda encarecidamente firmar las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utiliza la clase <xref:System.Xml.Serialization.XmlSerializer> con una clave protegida contra la divulgación. Esta recomendación se aplica cuando se realiza un modificador manual a <xref:System.Xml.Serialization.XmlSerializer> y cuando se lleva a cabo un modificador automático \(mediante Svcutil.exe, Agregar referencia de servicio o una herramienta similar\). Esto es debido a que el motor de serialización <xref:System.Xml.Serialization.XmlSerializer> admite la carga de *ensamblados de serialización pregenerados* siempre que se firmen con la misma clave que la aplicación. Una aplicación sin firma está totalmente desprotegida frente a la posibilidad de que un ensamblado malintencionado que coincida con el nombre esperado del ensamblado de serialización previamente generado se sitúe en la carpeta de aplicaciones o en la caché global de ensamblados. Por supuesto, antes de nada, un atacante debe tener acceso de escritura a una de estas dos ubicaciones para intentar realizar dicha acción.  
  
 Otra amenaza que existe siempre que usted utiliza <xref:System.Xml.Serialization.XmlSerializer> está relacionada con el acceso de escritura a la carpeta temporal del sistema. El motor de serialización <xref:System.Xml.Serialization.XmlSerializer> crea y utiliza *ensamblados de serialización* temporales en esta carpeta. Debería ser consciente de que cualquier proceso con acceso de escritura a la carpeta temporal puede sobrescribir estos ensamblados de serialización con código malintencionado.  
  
## Reglas para la compatibilidad de XmlSerializer  
 No puede aplicar directamente <xref:System.Xml.Serialization.XmlSerializer>\- los atributos compatibles a los parámetros de operación de contrato o valores devueltos. Sin embargo, se pueden aplicar a los mensajes con tipo \(partes del cuerpo del contrato de mensaje\), como se muestra en el código siguiente.  
  
 [!code-csharp[c_XmlSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#3)]
 [!code-vb[c_XmlSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#3)]  
  
 Cuando se aplica a los miembros de mensaje con tipo, estos atributos invalidan propiedades que están en conflicto en los atributos de mensaje con tipo. Por ejemplo en el siguiente código, `ElementName` invalida `Name`.  
  
 [!code-csharp[c_XmlSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#4)]
 [!code-vb[c_XmlSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#4)]  
  
 No se admite el atributo <xref:System.ServiceModel.MessageHeaderArrayAttribute> al utilizar <xref:System.Xml.Serialization.XmlSerializer>.  
  
> [!NOTE]
>  En este caso, <xref:System.Xml.Serialization.XmlSerializer> inicia la siguiente excepción, que se libera antes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]: "Los elementos declarados en el nivel superior de un esquema no pueden tener `maxOccurs` \> 1. Debe proporcionar un elemento contenedor para 'más' usando `XmlArray` o `XmlArrayItem` en lugar de `XmlElementAttribute`, o usando el estilo de parámetro Wrapped".  
>   
>  Si recibe esta excepción, investigue si se aplica esta situación.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite <xref:System.Xml.Serialization.SoapIncludeAttribute> ni atributos <xref:System.Xml.Serialization.XmlIncludeAttribute> en contratos de mensaje y contratos de operación; utilice, en su lugar, el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute>.  
  
## Tipos que implementan la interfaz IXmlSerializable  
 `IXmlSerializable`admite totalmente los tipos que implementan la interfaz `DataContractSerializer`. El atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> siempre se debería aplicar a estos tipos para controlar su esquema.  
  
> [!WARNING]
>  Si está serializando tipos polimórficos, debe aplicar el <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> al tipo para asegurarse de que se serializa el tipo correcto.  
  
 Existen tres variedades de tipos que implementan `IXmlSerializable`: tipos que representan el contenido arbitrario, tipos que representan un elemento único, y los tipos <xref:System.Data.DataSet> heredados.  
  
-   Los tipos de contenido utilizan un método de proveedor de esquema especificado por el atributo `XmlSchemaProviderAttribute`. El método no devuelve `null` y la propiedad <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A> en el atributo se deja como su valor predeterminado de `false`. Éste es el uso más común de los tipos `IXmlSerializable`.  
  
-   Se utilizan los tipos de elemento cuando un tipo `IXmlSerializable` debe controlar su propio nombre del elemento raíz. Para marcar un tipo como un tipo de elemento, establezca la propiedad <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A> del atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> en `true` o devuelva `null` a partir del método de proveedor de esquema. Tener un método de proveedor de esquema es opcional para los tipos de elemento. Puede especificar `null` en lugar del nombre del método en `XmlSchemaProviderAttribute`. Sin embargo, si `IsAny` es `true` y se especifica un método de proveedor de esquema, el método debe devolver `null`.  
  
-   Los tipos <xref:System.Data.DataSet> heredados son `IXmlSerializable` escribe que no se marca con el atributo `XmlSchemaProviderAttribute`. En su lugar, confían en el método <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> para la generación del esquema. Este patrón se utiliza para el tipo `DataSet` y su conjunto de datos con tipo deriva una clase en versiones anteriores de .NET Framework, pero ahora es obsoleto y sólo se admite por razones heredadas. No confíe en este patrón y aplique siempre `XmlSchemaProviderAttribute` a sus tipos `IXmlSerializable`.  
  
### Tipos de contenido de IXmlSerializable  
 Al serializar un miembro de datos de un tipo que implementa `IXmlSerializable`, y es un tipo de contenido como el que se ha definido previamente, el serializador escribe el elemento contenedor para el miembro de datos y pasará el control al método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>. La implementación <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> puede escribir cualquier XML, incluso agregar los atributos al elemento contenedor. Una vez realizado `WriteXml`, el serializador cierra el elemento.  
  
 Al deserializar un miembro de datos de un tipo que implementa `IXmlSerializable`, y es un tipo de contenido como el que se ha definido previamente, el deserializador sitúa el lector de XML en el elemento contenedor para el miembro de datos y pasa el control al método <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>. El método debe leer todo el elemento, también las etiquetas de cierre e inicio. Asegúrese de que su código `ReadXml` controla el caso donde el elemento está vacío. Además, su implementación `ReadXml` no debería confiar en el elemento contenedor denominado de una manera determinada. El serializador elige el nombre y este puede variar.  
  
 Se permite asignar polimórficamente tipos de contenido `IXmlSerializable`, por ejemplo, a los miembros de datos de tipo <xref:System.Object>. También se permite que las instancias de tipo sean nulo. Finalmente, es posible utilizar los tipos `IXmlSerializable` con preservación de gráfico de objetos habilitado y con <xref:System.Runtime.Serialization.NetDataContractSerializer>. Todas estas características exigen al serializador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que adjunte ciertos atributos en el elemento contenedor \("nil "y "type" en el espacio de nombres de instancia del Esquema XML e "Id", "Ref", "Type" y "Assembly" en un espacio de nombres específico de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\).  
  
#### Atributos que hay que omitir al Implementar ReadXml  
 Antes de pasar el control al código `ReadXml`, el deserializador examina el elemento XML, detecta estos atributos XML especiales y actúa sobre ellos. Por ejemplo, si "nil" es `true`, se deserializa un valor null y no se llama a `ReadXml`. Si se detecta polimorfismo, el contenido del elemento se deserializa como si fuera un tipo diferente. Se llama a la implementación del tipo asignado polimórficamente `ReadXml`. En cualquier caso, una implementación de `ReadXml` debería omitir estos atributos especiales ya que están controlados por el deserializador.  
  
### Consideraciones del esquema para los tipos de contenido de IXmlSerializable  
 Al exportar el esquema y un tipo de contenido `IXmlSerializable`, se llama al método de proveedor de esquema.<xref:System.Xml.Schema.XmlSchemaSet> se pasa al método de proveedor de esquema. El método puede agregar cualquier esquema válido al conjunto de esquemas. El conjunto de esquemas contiene el esquema conocido en el momento de la exportación del esquema. Cuando el método de proveedor de esquema debe agregar un elemento al conjunto de esquemas, debe determinar si en el esquema ya existe un <xref:System.Xml.Schema.XmlSchema> con el espacio de nombres adecuado. Si ya existe, el método de proveedor de esquema debe agregar el nuevo elemento al `XmlSchema` existente. De lo contrario, debe crear una nueva instancia `XmlSchema`. Esto es importante si se utilizan las matrices de los tipos `IXmlSerializable`. Por ejemplo, si tiene un tipo `IXmlSerializable` que se exporta como tipo "A" en el espacio de nombres "B", es posible que cuando al llamar al método de proveedor de esquema, el conjunto de esquemas ya contenga el esquema para que "B" incluya el tipo "ArrayOfA."  
  
 Además de agregar los tipos a <xref:System.Xml.Schema.XmlSchemaSet>, el método de proveedor de esquema para los tipos de contenido debe devolver un valor no nulo. Puede devolver un <xref:System.Xml.XmlQualifiedName> que especifique el nombre del tipo de esquema que se utilizará para el tipo `IXmlSerializable` concreto. Este nombre completo también actúa como el nombre de contrato de datos y el espacio de nombres del tipo. Se permite devolver un tipo que no existe en el esquema establecido inmediatamente cuando vuelve el método del proveedor de esquema. No obstante, se espera que en el momento de exportar todos los tipos relacionados \(se llama al método <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A> para todos los tipos relevantes en el <xref:System.Runtime.Serialization.XsdDataContractExporter>, y se tiene acceso a la propiedad <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A>\), el tipo existirá en el conjunto de esquemas. Teniendo acceso a la propiedad `Schemas` antes de que se hayan realizado todas las llamadas `Export` pertinentes puede producir <xref:System.Xml.Schema.XmlSchemaException>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] el proceso de exportación, consulte [Exportación de esquemas desde las clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
 El método de proveedor de esquema también puede devolver el <xref:System.Xml.Schema.XmlSchemaType> que se va a utilizar. El tipo puede o no ser anónimo. Si es anónimo, el esquema para el tipo `IXmlSerializable` se exporta como tipo anónimo cada vez que el tipo `IXmlSerializable` se utiliza como un miembro de datos. El tipo `IXmlSerializable` aún tiene un nombre de contrato de datos y un espacio de nombres. \(Esto se determina como se ha descrito en [Nombres de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-names.md), excepto que el atributo <xref:System.Runtime.Serialization.DataContractAttribute> no se puede usar para personalizar el nombre\). Si no es anónimo, debe ser uno de los tipos en `XmlSchemaSet`. Este caso es equivalente a la devolución del `XmlQualifiedName` del tipo.  
  
 Además, se exporta una declaración de elemento global para el tipo. Si el tipo no tiene el atributo <xref:System.Xml.Serialization.XmlRootAttribute> aplicado, el elemento tiene el mismo nombre y espacio de nombres que el contrato de datos, y su propiedad "nillable" será `true`. La única excepción es el espacio de nombres de esquema \("http:\/\/www.w3.org\/2001\/XMLSchema"\). Si el contrato de datos del tipo está en este espacio de nombres, el elemento global correspondiente está en el espacio de nombres en blanco porque no está permitido agregar nuevos elementos al espacio de nombres del esquema. Si el tipo tiene el atributo `XmlRootAttribute` aplicado, la declaración del elemento global se exporta mediante las siguientes propiedades: <xref:System.Xml.Serialization.XmlRootAttribute.ElementName%2A>, <xref:System.Xml.Serialization.XmlRootAttribute.Namespace%2A> y <xref:System.Xml.Serialization.XmlRootAttribute.IsNullable%2A>. Los valores predeterminados con `XmlRootAttribute` aplicados son el nombre de contrato de datos, un espacio de nombres en blanco y "nillable" como `true`.  
  
 Las mismas reglas de la declaración de elemento globales se aplican a los tipos de conjunto de datos heredados. Tenga en cuenta que `XmlRootAttribute` no puede invalidar declaraciones de elemento globales agregadas a través de código personalizado, o agregadas a `XmlSchemaSet` mediante el método de proveedor de esquema o a través de `GetSchema` para los tipos de conjunto de datos heredados.  
  
### Tipos de elemento de IXmlSerializable  
 Los tipos de elemento `IXmlSerializable` hacen que la propiedad `IsAny` se establezca en `true` o hacen que su método de proveedor de esquema se vuelva `null`.  
  
 Serializar y deserializar un tipo de elemento es muy similar a serializar y deserializar un tipo de contenido. Sin embargo, hay algunas diferencias importantes:  
  
-   Se espera que la implementación `WriteXml` escriba exactamente un elemento \(qué podría contener, por supuesto, varios elementos secundarios\). No debería estar escribiendo los atributos fuera de este elemento único, varios elementos del mismo nivel o contenido mixto. El elemento puede estar vacío.  
  
-   La implementación `ReadXml` no debería leer el elemento contenedor. Se espera que lea el un elemento que `WriteXml` genera.  
  
-   Al serializar de manera regular un tipo de elemento \(por ejemplo, como un miembro de datos en un contrato de datos\), el serializador producirá un elemento contenedor antes de llamar a `WriteXml`, como en los tipos de contenido. No obstante, al serializar un tipo de elemento en el nivel superior, normalmente, el serializador no produce un elemento contenedor alrededor del elemento que `WriteXml` escribe, salvo que se especifiquen explícitamente un nombre de raíz y un espacio de nombres al construir el serializador en los constructores `DataContractSerializer` o `NetDataContractSerializer`.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).  
  
-   Cuando se serializa un tipo de elemento en el nivel superior sin especificar el nombre de raíz y el espacio de nombres en el momento de la construcción, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> no hacen prácticamente nada, y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A> llama a `WriteXml`. En este modo, el objeto que se serializa no puede ser `null` y no se puede asignar polimórficamente. Además, la preservación del gráfico de objetos puede se puede habilitar y no se puede utilizar `NetDataContractSerializer`.  
  
-   Al deserializar un tipo de elemento en el nivel superior sin especificar el nombre y el espacio de nombres raíz en el momento de la construcción, <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> devuelve `true` si encuentra el inicio de cualquier elemento.<xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> con el parámetro `verifyObjectName` establecido en `true` se comporta igual que `IsStartObject` antes realmente de leer el objeto realmente.`ReadObject` después pasa el control al método `ReadXml`.  
  
 El esquema exportado para los tipos de elemento es igual que para el tipo `XmlElement` tal y como se ha descrito en una sección anterior, excepto que el método de proveedor de esquema puede agregar un esquema adicional a <xref:System.Xml.Schema.XmlSchemaSet> como con los tipos de contenido. No se permite utilizar el atributo `XmlRootAttribute` con tipos de elemento y las declaraciones de elemento globales nunca se emiten para estos tipos.  
  
### Diferencias respecto a XmlSerializer  
 `IXmlSerializable` entiende también la interfaz `XmlSchemaProviderAttribute` y `XmlRootAttribute` y los atributos <xref:System.Xml.Serialization.XmlSerializer>. Sin embargo, hay algunas diferencias en cómo se tratan estos en el modelo del contrato de datos. Las principales diferencias se resumen en la lista siguiente:  
  
-   El método de proveedor de esquema debe ser público para ser utilizable en `XmlSerializer`, pero no tiene que ser público para ser utilizable en el modelo del contrato de datos.  
  
-   Se llama al método de proveedor de esquema cuando `IsAny` es `true` en el modelo del contrato de datos pero no con `XmlSerializer`.  
  
-   Cuando el atributo `XmlRootAttribute` no está presente para contenido o tipos de conjunto de datos heredados, `XmlSerializer` exporta una declaración de elemento global en el espacio de nombres en blanco. En el modelo del contrato de datos, el espacio de nombres utilizado es normalmente el espacio de nombres de contrato de datos, tal y como se ha descrito anteriormente.  
  
 Tenga en cuenta estas diferencias cuando cree tipos que se utilizan con ambas tecnologías de serialización.  
  
### Importar el esquema de IXmlSerializable  
 Al importar un esquema generado a partir de los tipos `IXmlSerializable`, existen pocas posibilidades:  
  
-   El esquema generado puede ser un esquema de contrato de datos válido, como se describe en [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). En este caso, el esquema puede importarse como de costumbre y se generarán los tipos de contrato de datos normales.  
  
-   El esquema generado no puede ser un esquema de contrato de datos válido. Por ejemplo, su método de proveedor de esquema puede generar un esquema que incluye atributos XML que no se admiten en el modelo de contrato de datos. En este caso, puede importar el esquema como tipos `IXmlSerializable`. Este modo de importación no está habilitado de forma predeterminada, pero se puede habilitar con facilidad. Por ejemplo, con el modificador de la línea de comandos `/importXmlTypes` a [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Esto se describe con más detalle en [Importación del esquema para generar clases](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md). Tenga en cuenta que debe trabajar directamente con XML para sus instancias de tipo. También puede considerar la utilización de una tecnología de serialización diferente que admita una gama más amplia de esquemas. Vea el tema acerca de la utilización del `XmlSerializer`.  
  
-   Puede desear volver a usar sus tipos `IXmlSerializable` existentes en el proxy en lugar de generar nuevos. En este caso, la característica de tipos a la cual s se hace referencia descrita en el tema Esquema de Importación para generar Tipos se puede utilizar para indicar el tipo que se reutilizará. Esto se corresponde con el uso del modificador `/reference` en svcutil.exe, que especifica el ensamblado que contiene los tipos que se van a volver a usar.  
  
### Comportamiento heredado de XmlSerializer  
 En .NET Framework 4.0.0 y versiones anteriores, XmlSerializer generaba ensamblados temporales de serialización escribiendo código de C\# en un archivo. El archivo se compiló en un ensamblado.  Este comportamiento tenía algunas consecuencias no deseadas como la reducción del tiempo de inicio para el serializador. En .NET Framework 4.0.5, este comportamiento se cambió para generar los ensamblados sin que sea necesario el uso del compilador. Algunos desarrolladores quizás deseen ver el código de C\# generado. Puede especificar usar este comportamiento heredado mediante la siguiente configuración:  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer tempFilesLocation='e:\temp\XmlSerializerBug' useLegacySerializerGeneration="true" />  
  </system.xml.serialization>  
  <system.diagnostics>  
    <switches>  
      <add name="XmlSerialization.Compilation" value="1" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.DataContractFormatAttribute>   
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Xml.Serialization.XmlSerializer>   
 <xref:System.ServiceModel.MessageHeaderArrayAttribute>   
 [Especificación de transferencia de datos en contratos de servicio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)   
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Cómo: Mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)