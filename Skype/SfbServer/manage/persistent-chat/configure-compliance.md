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
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="85417-103">Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="85417-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="85417-104">**Resumen:** Obtenga información sobre cómo configurar el servicio de cumplimiento del servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="85417-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="85417-105">El cumplimiento de chat persistente permite a los administradores mantener un archivo de mensajes de chat persistente, así como actividades.</span><span class="sxs-lookup"><span data-stu-id="85417-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="85417-106">El servicio de cumplimiento registra y archiva datos relacionados con cada conversación del servidor de chat persistente, incluido el momento en que un participante:</span><span class="sxs-lookup"><span data-stu-id="85417-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="85417-107">Se une a un salón de chat persistente</span><span class="sxs-lookup"><span data-stu-id="85417-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="85417-108">Sale de un salón de chat</span><span class="sxs-lookup"><span data-stu-id="85417-108">Leaves a chat room</span></span>

- <span data-ttu-id="85417-109">Publica un mensaje</span><span class="sxs-lookup"><span data-stu-id="85417-109">Posts a message</span></span>

- <span data-ttu-id="85417-110">Ver el historial de chat</span><span class="sxs-lookup"><span data-stu-id="85417-110">Views chat history</span></span>

- <span data-ttu-id="85417-111">Carga un archivo</span><span class="sxs-lookup"><span data-stu-id="85417-111">Uploads a file</span></span>

- <span data-ttu-id="85417-112">Descarga un archivo</span><span class="sxs-lookup"><span data-stu-id="85417-112">Downloads a file</span></span>

<span data-ttu-id="85417-113">Esta información se puede recuperar de la base de datos de cumplimiento SQL según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="85417-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="85417-114">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="85417-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="85417-115">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="85417-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="85417-116">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="85417-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="85417-117">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="85417-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="85417-118">Configurar el servicio de cumplimiento mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85417-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="85417-119">Una vez habilitado el servicio de cumplimiento mediante el Generador de topologías, puede configurar el servicio con el cmdlet **Set-CsPersistenChatComplianceConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="85417-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="85417-120">o</span><span class="sxs-lookup"><span data-stu-id="85417-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="85417-121">Puede establecer los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="85417-121">You can set the following parameters:</span></span>

- <span data-ttu-id="85417-122">AdapterType: permite especificar el tipo de adaptador.</span><span class="sxs-lookup"><span data-stu-id="85417-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="85417-123">Un adaptador es un producto de terceros que convierte los datos de la base de datos de cumplimiento a un formato específico.</span><span class="sxs-lookup"><span data-stu-id="85417-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="85417-124">XML es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="85417-124">XML is the default.</span></span>

- <span data-ttu-id="85417-125">OneChatRoomPerOutputFile: este parámetro le permite especificar que se crearán informes independientes para cada salón de chat.</span><span class="sxs-lookup"><span data-stu-id="85417-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="85417-126">AddChatRoomDetails: cuando se habilita, este parámetro registra detalles adicionales sobre cada salón de chat de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="85417-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="85417-127">Dado que esta configuración puede aumentar considerablemente el tamaño de la base de datos, está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="85417-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="85417-128">AddUserDetails: cuando está habilitado, este parámetro registra detalles adicionales sobre cada usuario del salón de chat en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="85417-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="85417-129">Dado que esta configuración puede aumentar considerablemente el tamaño de la base de datos, está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="85417-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="85417-130">Identidad: este parámetro permite establecer el ámbito de la configuración de cumplimiento para una colección determinada, incluidos los niveles global, de sitio y de servicio.</span><span class="sxs-lookup"><span data-stu-id="85417-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="85417-131">El valor predeterminado es el nivel global.</span><span class="sxs-lookup"><span data-stu-id="85417-131">The default is the global level.</span></span> 

- <span data-ttu-id="85417-132">RunInterval: este parámetro determina la cantidad de tiempo antes de que el servidor cree el siguiente archivo de salida de cumplimiento (el valor predeterminado es 15 minutos).</span><span class="sxs-lookup"><span data-stu-id="85417-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="85417-133">Usar un adaptador de cumplimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="85417-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="85417-134">Puede escribir un adaptador personalizado en lugar de usar El XmlAdapter que se instala con el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="85417-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="85417-135">Para ello, debe proporcionar un ensamblado de .NET Framework que contenga una clase pública que implemente la **interfaz IComplianceAdapter.**</span><span class="sxs-lookup"><span data-stu-id="85417-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="85417-136">Debe colocar este ensamblado en la carpeta de instalación del servidor de chat persistente de cada servidor del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="85417-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="85417-137">Cualquiera de los servidores de cumplimiento puede proporcionar datos de cumplimiento al adaptador, pero los servidores de cumplimiento no proporcionarán datos de cumplimiento duplicados a varias instancias del adaptador.</span><span class="sxs-lookup"><span data-stu-id="85417-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="85417-138">La interfaz se define en el ensamblado Compliance.dll en el espacio de nombres  `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="85417-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="85417-139">La interfaz define dos métodos que el adaptador personalizado debe implementar.</span><span class="sxs-lookup"><span data-stu-id="85417-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="85417-140">El servidor de cumplimiento de chat persistente llamará al método siguiente cuando el adaptador se cargue por primera vez.</span><span class="sxs-lookup"><span data-stu-id="85417-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="85417-141">Contiene  `AdapterConfig` la configuración de cumplimiento de chat persistente que es relevante para el adaptador de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="85417-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="85417-142">El servidor de cumplimiento de chat persistente llama al siguiente método a intervalos periódicos, siempre y cuando haya nuevos datos para traducir.</span><span class="sxs-lookup"><span data-stu-id="85417-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="85417-143">Este intervalo de tiempo es igual al establecido en la  `RunInterval` configuración de cumplimiento de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="85417-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="85417-144">Contiene  `ConversationCollection` la información de conversación que se recopiló desde la última vez que se llamó a este método.</span><span class="sxs-lookup"><span data-stu-id="85417-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="85417-145">Personalizar el archivo de definición XSLT</span><span class="sxs-lookup"><span data-stu-id="85417-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="85417-146">Los datos de cumplimiento se entregan como XML, que puede transformar en el formato que mejor se adapte a su organización, mediante un archivo de definición XSLT.</span><span class="sxs-lookup"><span data-stu-id="85417-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="85417-147">Este tema describe el archivo XML que crea el Servicio de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="85417-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="85417-148">También proporciona ejemplos de archivos de definición XSLT y de salida.</span><span class="sxs-lookup"><span data-stu-id="85417-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="85417-149">Formato de salida</span><span class="sxs-lookup"><span data-stu-id="85417-149">Output format</span></span>

<span data-ttu-id="85417-150">El resultado del servicio de cumplimiento se clasifica por conversación (el elemento Conversation) y, a continuación, por mensaje (el elemento Messages), como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="85417-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

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

<span data-ttu-id="85417-151">Un elemento Conversation contiene cuatro elementos (Channel, FirstMessage, StartTimeUTC y EndTimeUTC).</span><span class="sxs-lookup"><span data-stu-id="85417-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="85417-152">El elemento Channel contiene el Identificador uniforme de recursos (URI) de la sala de chat, mientras que el elemento FirstMessage describe el primer mensaje del elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="85417-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="85417-153">Los elementos StartTimeUTC y EndTimeUTC proporcionan las horas de inicio y finalización de la conversación, como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="85417-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="85417-154">Un elemento Message contiene dos elementos (Sender y DateTimeUTC) y tres atributos (Type, Content e ID).</span><span class="sxs-lookup"><span data-stu-id="85417-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="85417-155">El elemento Sender representa el usuario que envía el mensaje y el elemento DateTimeUTC representa cuándo se produce un evento, como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="85417-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="85417-156">En la tabla siguiente se describen los atributos de mensaje Type, Content e ID.</span><span class="sxs-lookup"><span data-stu-id="85417-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="85417-157">**Atributos del elemento Messages**</span><span class="sxs-lookup"><span data-stu-id="85417-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="85417-158">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="85417-158">**Attribute**</span></span>|<span data-ttu-id="85417-159">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="85417-159">**Description**</span></span>|<span data-ttu-id="85417-160">**Opcional/Obligatorio**</span><span class="sxs-lookup"><span data-stu-id="85417-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85417-161">Tipo</span><span class="sxs-lookup"><span data-stu-id="85417-161">Type</span></span>  <br/> |<span data-ttu-id="85417-p114">Especifica el tipo de mensaje. Los tipos de mensaje se describen en la tabla Tipos de mensaje de los elmentos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="85417-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="85417-164">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="85417-164">Required</span></span>  <br/> |
|<span data-ttu-id="85417-165">Contenido</span><span class="sxs-lookup"><span data-stu-id="85417-165">Content</span></span>  <br/> |<span data-ttu-id="85417-p115">Contiene el contenido del mensaje. Aquellos mensajes que presenten el tipo Join o Part no usan este atributo.</span><span class="sxs-lookup"><span data-stu-id="85417-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="85417-168">Opcional</span><span class="sxs-lookup"><span data-stu-id="85417-168">Optional</span></span>  <br/> |
|<span data-ttu-id="85417-169">ID</span><span class="sxs-lookup"><span data-stu-id="85417-169">ID</span></span>  <br/> |<span data-ttu-id="85417-p116">Especifica el Id. único del contenido. Este atributo solo se usa cuando los mensajes son del tipo Chat.</span><span class="sxs-lookup"><span data-stu-id="85417-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="85417-172">Opcional</span><span class="sxs-lookup"><span data-stu-id="85417-172">Optional</span></span>  <br/> |

<span data-ttu-id="85417-p117">Cada elemento Sender contiene cinco atributos: nombre de usuario, Id., correo electrónico, interno y URI. Estos atributos se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="85417-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="85417-175">**Atributos del elemento Sender**</span><span class="sxs-lookup"><span data-stu-id="85417-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="85417-176">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="85417-176">**Attribute**</span></span>|<span data-ttu-id="85417-177">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="85417-177">**Description**</span></span>|<span data-ttu-id="85417-178">**Opcional/Obligatorio**</span><span class="sxs-lookup"><span data-stu-id="85417-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85417-179">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="85417-179">Username</span></span>  <br/> |<span data-ttu-id="85417-180">El nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="85417-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="85417-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="85417-181">Optional</span></span>  <br/> |
|<span data-ttu-id="85417-182">ID</span><span class="sxs-lookup"><span data-stu-id="85417-182">ID</span></span>  <br/> |<span data-ttu-id="85417-183">Identificador único del remitente.</span><span class="sxs-lookup"><span data-stu-id="85417-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="85417-184">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="85417-184">Required</span></span>  <br/> |
|<span data-ttu-id="85417-185">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="85417-185">Email</span></span>  <br/> |<span data-ttu-id="85417-186">La dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="85417-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="85417-187">Opcional</span><span class="sxs-lookup"><span data-stu-id="85417-187">Optional</span></span>  <br/> |
|<span data-ttu-id="85417-188">Interno</span><span class="sxs-lookup"><span data-stu-id="85417-188">Internal</span></span>  <br/> |<span data-ttu-id="85417-p118">Determina si el usuario es un usuario interno o un usuario federado. Si el valor está establecido en true, el usuario es interno.</span><span class="sxs-lookup"><span data-stu-id="85417-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="85417-191">Opcional</span><span class="sxs-lookup"><span data-stu-id="85417-191">Optional</span></span>  <br/> |
|<span data-ttu-id="85417-192">Uri</span><span class="sxs-lookup"><span data-stu-id="85417-192">Uri</span></span>  <br/> |<span data-ttu-id="85417-193">URI del SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="85417-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="85417-194">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="85417-194">Required</span></span>  <br/> |

<span data-ttu-id="85417-195">En los ejemplos siguientes se muestran los tipos de mensaje que puede contener el elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="85417-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="85417-196">Contiene ejemplos también de la forma en la que se usa cada elemento.</span><span class="sxs-lookup"><span data-stu-id="85417-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="85417-197">Unirse: un usuario se une a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="85417-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="85417-198">Parte: un usuario sale de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="85417-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="85417-199">Chat: dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="85417-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="85417-200">Backchat: un usuario solicita contenido del historial de chat.</span><span class="sxs-lookup"><span data-stu-id="85417-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="85417-201">Carga de archivos: un usuario carga un archivo.</span><span class="sxs-lookup"><span data-stu-id="85417-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="85417-202">Descarga de archivos: un usuario descarga un archivo.</span><span class="sxs-lookup"><span data-stu-id="85417-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="85417-203">XSD de salida de chat persistente predeterminado y transformación XSL de ejemplo</span><span class="sxs-lookup"><span data-stu-id="85417-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="85417-204">El ejemplo de código siguiente contiene el resultado predeterminado del servidor de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="85417-204">The following code sample contains the default output from the Compliance Server:</span></span>

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

<span data-ttu-id="85417-205">El ejemplo de código siguiente contiene una transformación XSL de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="85417-205">The following code sample contains a sample XSL transform:</span></span>

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
