---
title: Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Resumen: obtenga información sobre cómo configurar el servicio de cumplimiento del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815070"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015

**Resumen:** Obtenga información sobre cómo configurar el servicio de cumplimiento del servidor de chat persistente en Skype Empresarial Server 2015.

El cumplimiento de chat persistente permite a los administradores mantener un archivo de mensajes de chat persistente, así como actividades. El servicio de cumplimiento registra y archiva datos relacionados con cada conversación del servidor de chat persistente, incluido el momento en que un participante:

- Se une a un salón de chat persistente

- Sale de un salón de chat

- Publica un mensaje

- Ver el historial de chat

- Carga un archivo

- Descarga un archivo

Esta información se puede recuperar de la base de datos de cumplimiento SQL según sea necesario. 

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurar el servicio de cumplimiento mediante Windows PowerShell

Una vez habilitado el servicio de cumplimiento mediante el Generador de topologías, puede configurar el servicio con el cmdlet **Set-CsPersistenChatComplianceConfiguration:**

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

o

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Puede establecer los siguientes parámetros:

- AdapterType: permite especificar el tipo de adaptador. Un adaptador es un producto de terceros que convierte los datos de la base de datos de cumplimiento a un formato específico. XML es el valor predeterminado.

- OneChatRoomPerOutputFile: este parámetro le permite especificar que se crearán informes independientes para cada salón de chat.

- AddChatRoomDetails: cuando se habilita, este parámetro registra detalles adicionales sobre cada salón de chat de la base de datos. Dado que esta configuración puede aumentar considerablemente el tamaño de la base de datos, está deshabilitada de forma predeterminada.

- AddUserDetails: cuando está habilitado, este parámetro registra detalles adicionales sobre cada usuario del salón de chat en la base de datos. Dado que esta configuración puede aumentar considerablemente el tamaño de la base de datos, está deshabilitada de forma predeterminada.

- Identidad: este parámetro permite establecer el ámbito de la configuración de cumplimiento para una colección determinada, incluidos los niveles global, de sitio y de servicio. El valor predeterminado es el nivel global. 

- RunInterval: este parámetro determina la cantidad de tiempo antes de que el servidor cree el siguiente archivo de salida de cumplimiento (el valor predeterminado es 15 minutos).

## <a name="use-a-customized-compliance-adapter"></a>Usar un adaptador de cumplimiento personalizado

Puede escribir un adaptador personalizado en lugar de usar El XmlAdapter que se instala con el servidor de chat persistente. Para ello, debe proporcionar un ensamblado de .NET Framework que contenga una clase pública que implemente la **interfaz IComplianceAdapter.** Debe colocar este ensamblado en la carpeta de instalación del servidor de chat persistente de cada servidor del grupo de servidores de chat persistente. Cualquiera de los servidores de cumplimiento puede proporcionar datos de cumplimiento al adaptador, pero los servidores de cumplimiento no proporcionarán datos de cumplimiento duplicados a varias instancias del adaptador.

La interfaz se define en el ensamblado Compliance.dll en el espacio de nombres  `Microsoft.Rtc.Internal.Chat.Server.Compliance` . La interfaz define dos métodos que el adaptador personalizado debe implementar.

El servidor de cumplimiento de chat persistente llamará al método siguiente cuando el adaptador se cargue por primera vez. Contiene  `AdapterConfig` la configuración de cumplimiento de chat persistente que es relevante para el adaptador de cumplimiento:

```cpp
void SetConfig(AdapterConfig config)
```

El servidor de cumplimiento de chat persistente llama al siguiente método a intervalos periódicos, siempre y cuando haya nuevos datos para traducir. Este intervalo de tiempo es igual al establecido en la  `RunInterval` configuración de cumplimiento de chat persistente:

```cpp
void Translate(ConversationCollection conversations)
```

Contiene  `ConversationCollection` la información de conversación que se recopiló desde la última vez que se llamó a este método.

## <a name="customize-the-xslt-definition-file"></a>Personalizar el archivo de definición XSLT

Los datos de cumplimiento se entregan como XML, que puede transformar en el formato que mejor se adapte a su organización, mediante un archivo de definición XSLT. Este tema describe el archivo XML que crea el Servicio de cumplimiento. También proporciona ejemplos de archivos de definición XSLT y de salida.

### <a name="output-format"></a>Formato de salida

El resultado del servicio de cumplimiento se clasifica por conversación (el elemento Conversation) y, a continuación, por mensaje (el elemento Messages), como se muestra en el siguiente ejemplo de código:

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Un elemento Conversation contiene cuatro elementos (Channel, FirstMessage, StartTimeUTC y EndTimeUTC). El elemento Channel contiene el Identificador uniforme de recursos (URI) de la sala de chat, mientras que el elemento FirstMessage describe el primer mensaje del elemento Messages. Los elementos StartTimeUTC y EndTimeUTC proporcionan las horas de inicio y finalización de la conversación, como se muestra en el siguiente ejemplo de código:

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Un elemento Message contiene dos elementos (Sender y DateTimeUTC) y tres atributos (Type, Content e ID). El elemento Sender representa el usuario que envía el mensaje y el elemento DateTimeUTC representa cuándo se produce un evento, como se muestra en el siguiente ejemplo de código:

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

En la tabla siguiente se describen los atributos de mensaje Type, Content e ID.

**Atributos del elemento Messages**

|**Atributo**|**Descripción**|**Opcional/Obligatorio**|
|:-----|:-----|:-----|
|Tipo  <br/> |Especifica el tipo de mensaje. Los tipos de mensaje se describen en la tabla Tipos de mensaje de los elmentos de mensaje.  <br/> |Obligatorio  <br/> |
|Contenido  <br/> |Contiene el contenido del mensaje. Aquellos mensajes que presenten el tipo Join o Part no usan este atributo.  <br/> |Opcional  <br/> |
|Id.  <br/> |Especifica el Id. único del contenido. Este atributo solo se usa cuando los mensajes son del tipo Chat.  <br/> |Opcional  <br/> |

Cada elemento Sender contiene cinco atributos: nombre de usuario, Id., correo electrónico, interno y URI. Estos atributos se describen en la siguiente tabla.

**Atributos del elemento Sender**

|**Atributo**|**Descripción**|**Opcional/Obligatorio**|
|:-----|:-----|:-----|
|Nombre de usuario  <br/> |El nombre de la regla.  <br/> |Opcional  <br/> |
|Id.  <br/> |Identificador único del remitente.  <br/> |Obligatorio  <br/> |
|Correo electrónico  <br/> |La dirección de correo electrónico del remitente.  <br/> |Opcional  <br/> |
|Interno  <br/> |Determina si el usuario es un usuario interno o un usuario federado. Si el valor está establecido en true, el usuario es interno.  <br/> |Opcional  <br/> |
|Uri  <br/> |URI del SIP del usuario.  <br/> |Obligatorio  <br/> |

En los ejemplos siguientes se muestran los tipos de mensaje que puede contener el elemento Messages. Contiene ejemplos también de la forma en la que se usa cada elemento.

Unirse: un usuario se une a un salón de chat.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Parte: un usuario sale de un salón de chat.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Chat: dirección de correo electrónico del remitente.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat: un usuario solicita contenido del historial de chat.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Carga de archivos: un usuario carga un archivo.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Descarga de archivos: un usuario descarga un archivo.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD de salida de chat persistente predeterminado y transformación XSL de ejemplo

El ejemplo de código siguiente contiene el resultado predeterminado del servidor de cumplimiento:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

El ejemplo de código siguiente contiene una transformación XSL de ejemplo:

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
