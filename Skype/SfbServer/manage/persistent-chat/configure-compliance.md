---
title: Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Resumen: Obtenga información sobre cómo configurar el servicio de cumplimiento de servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 99c09408fbc404edd7ccd6c3844f59dca77a35f0
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568629"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5a571-103">Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a571-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5a571-104">**Resumen:** Obtenga información sobre cómo configurar el servicio de cumplimiento de servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a571-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5a571-105">El cumplimiento del chat persistente permite a los administradores mantener un archivo de las actividades y de los mensajes del chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5a571-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="5a571-106">El servicio de cumplimiento registra y archiva datos relacionados con cada conversación de servidor de Chat persistente, incluso cuando un participante:</span><span class="sxs-lookup"><span data-stu-id="5a571-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>
  
- <span data-ttu-id="5a571-107">Se une a un salón de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="5a571-107">Joins a Persistent Chat room</span></span>
    
- <span data-ttu-id="5a571-108">Abandone un salón de chat</span><span class="sxs-lookup"><span data-stu-id="5a571-108">Leaves a chat room</span></span>
    
- <span data-ttu-id="5a571-109">Publique un mensaje</span><span class="sxs-lookup"><span data-stu-id="5a571-109">Posts a message</span></span>
    
- <span data-ttu-id="5a571-110">Vea el historial de chat</span><span class="sxs-lookup"><span data-stu-id="5a571-110">Views chat history</span></span>
    
- <span data-ttu-id="5a571-111">Cargue un archivo</span><span class="sxs-lookup"><span data-stu-id="5a571-111">Uploads a file</span></span>
    
- <span data-ttu-id="5a571-112">Descargue un archivo</span><span class="sxs-lookup"><span data-stu-id="5a571-112">Downloads a file</span></span>
    
<span data-ttu-id="5a571-113">Según sea necesario, esta información se puede recuperar de la base de datos de SQL de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5a571-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 
  
## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="5a571-114">Configurar el servicio de cumplimiento con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a571-114">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="5a571-115">Una vez que el servicio de cumplimiento se ha habilitado con el Generador de topologías, puede configurar el servicio con el cmdlet **Set-CsPersistenChatComplianceConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="5a571-115">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="5a571-116">o</span><span class="sxs-lookup"><span data-stu-id="5a571-116">or</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="5a571-117">Puede establecer los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="5a571-117">You can set the following parameters:</span></span>
  
- <span data-ttu-id="5a571-118">AdapterType: permite especificar el tipo de adaptador.</span><span class="sxs-lookup"><span data-stu-id="5a571-118">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="5a571-119">Un adaptador es un producto de terceros que convierte los datos en la base de datos de cumplimiento en un formato específico.</span><span class="sxs-lookup"><span data-stu-id="5a571-119">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="5a571-120">La opción predeterminada es XML.</span><span class="sxs-lookup"><span data-stu-id="5a571-120">XML is the default.</span></span>
    
- <span data-ttu-id="5a571-121">OneChatRoomPerOutputFile - este parámetro permite especificar que separar los informes que se creará para cada salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5a571-121">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>
    
- <span data-ttu-id="5a571-122">AddChatRoomDetails: cuando se habilita, este parámetro registra los detalles adicionales sobre cada salón de chat en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5a571-122">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="5a571-123">Como esta configuración puede aumentar en gran medida el tamaño de la base de datos, se encuentra deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a571-123">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="5a571-124">AddUserDetails: cuando se habilita, este parámetro registra los detalles adicionales sobre cada usuario del salón de chat en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5a571-124">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="5a571-125">Como esta configuración puede aumentar en gran medida el tamaño de la base de datos, se encuentra deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a571-125">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="5a571-126">Identity: este parámetro permite limitar la configuración de cumplimiento a una colección en concreto, incluso de forma global, en el sitio o en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5a571-126">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="5a571-127">La opción predeterminada es el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="5a571-127">The default is the global level.</span></span> 
    
- <span data-ttu-id="5a571-128">RunInterval: este parámetro determina la cantidad de tiempo antes de que el servidor cree el siguiente archivo de salida de cumplimiento (el tiempo predeterminado es 15 minutos).</span><span class="sxs-lookup"><span data-stu-id="5a571-128">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>
    
## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="5a571-129">Usar un adaptador de cumplimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="5a571-129">Use a customized compliance adapter</span></span>

<span data-ttu-id="5a571-130">Puede escribir un adaptador personalizado en lugar de usar el XmlAdapter que se instala con el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5a571-130">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="5a571-131">Para lograr esto, es necesario brindar un ensamblado de .NET Framework que contenga una clase pública que implemente la interfaz de **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="5a571-131">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="5a571-132">Debe colocar este ensamblado en la carpeta de instalación del servidor de Chat persistente de cada servidor de su grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5a571-132">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="5a571-133">Cualquiera de los servidores de cumplimiento puede brindar datos de cumplimiento al adaptador, pero los servidores de cumplimiento no brindarán datos de cumplimiento duplicados a varias instancias del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5a571-133">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>
  
<span data-ttu-id="5a571-134">La interfaz se define en el ensamblado Compliance.dll en el espacio de nombres `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="5a571-134">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="5a571-135">La interfaz define dos métodos que el adaptador personalizado necesita implementar.</span><span class="sxs-lookup"><span data-stu-id="5a571-135">The interface defines two methods that your custom adapter must implement.</span></span>
  
<span data-ttu-id="5a571-136">El servidor de cumplimiento de Chat persistente llamará al método siguiente cuando se carga primero el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5a571-136">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="5a571-137">El `AdapterConfig` contiene la configuración de cumplimiento de Chat persistente que es relevante para el adaptador de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="5a571-137">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>
  
```
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="5a571-138">El servidor de cumplimiento de Chat persistente llama al método siguiente en intervalos periódicos siempre y cuando no hay datos nuevos para traducir.</span><span class="sxs-lookup"><span data-stu-id="5a571-138">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="5a571-139">Este intervalo de tiempo es igual a la `RunInterval` como se establece en la configuración de cumplimiento de Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="5a571-139">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>
  
```
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="5a571-140">El `ConversationCollection` contiene la información de conversación que se recopila desde la última vez que se llama a este método.</span><span class="sxs-lookup"><span data-stu-id="5a571-140">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>
  
## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="5a571-141">Personalizar el archivo de definición XSLT</span><span class="sxs-lookup"><span data-stu-id="5a571-141">Customize the XSLT definition file</span></span>

<span data-ttu-id="5a571-p110">Los datos de cumplimiento se proporcionan en formato XML, que puede convertir al formato que mejor se adapte a las necesidades de su organización, por medio de un archivo de definición XSLT. En este tema se describe el archivo XML que crea el Servicio de cumplimiento. También proporciona ejemplos de archivos de salida y de definición XSLT.</span><span class="sxs-lookup"><span data-stu-id="5a571-p110">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>
  
### <a name="output-format"></a><span data-ttu-id="5a571-145">Formato de resultados</span><span class="sxs-lookup"><span data-stu-id="5a571-145">Output format</span></span>

<span data-ttu-id="5a571-146">Los resultados del Servicio de cumplimiento se clasifican por conversación (el elemento Conversation) y, posteriormente, por mensaje (el elemento Messages), tal como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="5a571-146">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>
  
```
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

<span data-ttu-id="5a571-p111">Un elemento Conversation contiene cuatro elementos (Channel, FirstMessage, StartTimeUTC y EndTimeUTC). El elemento Channel contiene el Identificador uniforme de recursos (URI) del salón de chat, mientras que el elemento FirstMessage describe el primer mensaje del elemento Messages. Los elementos StartTimeUTC y EndTimeUTC contienen las horas de inicio y de finalización de la conversación, tal como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="5a571-p111">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>
  
```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="5a571-p112">Un elemento Message contiene dos elementos (Sender y DateTimeUTC) y tres atributos (Type, Content e ID). El elemento Sender representa el usuario que envía el mensaje, mientras que el elemento DateTimeUTC representa el momento en el que tiene lugar un evento, tal como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="5a571-p112">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="5a571-152">En la tabla siguiente se describen los atributos de mensaje Type, Content e ID.</span><span class="sxs-lookup"><span data-stu-id="5a571-152">The following table describes the message attributes Type, Content, and ID.</span></span>
  
<span data-ttu-id="5a571-153">**Atributos del elemento Messages**</span><span class="sxs-lookup"><span data-stu-id="5a571-153">**Messages Element Attributes**</span></span>

|<span data-ttu-id="5a571-154">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="5a571-154">**Attribute**</span></span>|<span data-ttu-id="5a571-155">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a571-155">**Description**</span></span>|<span data-ttu-id="5a571-156">**Necesario/opcional**</span><span class="sxs-lookup"><span data-stu-id="5a571-156">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a571-157">Type</span><span class="sxs-lookup"><span data-stu-id="5a571-157">Type</span></span>  <br/> |<span data-ttu-id="5a571-p113">Especifica el tipo de mensaje. Los tipos de mensajes se describen en la tabla Tipos de mensajes de los elementos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5a571-p113">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="5a571-160">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5a571-160">Required</span></span>  <br/> |
|<span data-ttu-id="5a571-161">Content</span><span class="sxs-lookup"><span data-stu-id="5a571-161">Content</span></span>  <br/> |<span data-ttu-id="5a571-p114">Contiene el contenido del mensaje. Aquellos mensajes que presenten el tipo Join o Part no usan este atributo.</span><span class="sxs-lookup"><span data-stu-id="5a571-p114">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="5a571-164">Opcional</span><span class="sxs-lookup"><span data-stu-id="5a571-164">Optional</span></span>  <br/> |
|<span data-ttu-id="5a571-165">ID</span><span class="sxs-lookup"><span data-stu-id="5a571-165">ID</span></span>  <br/> |<span data-ttu-id="5a571-p115">Especifica el identificador único del contenido. Este atributo solo se usa cuando los mensajes son del tipo Chat.</span><span class="sxs-lookup"><span data-stu-id="5a571-p115">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="5a571-168">Opcional</span><span class="sxs-lookup"><span data-stu-id="5a571-168">Optional</span></span>  <br/> |
   
<span data-ttu-id="5a571-p116">Cada elemento Sender contiene cinco atributos: user name, ID, email, internal y URI. Estos atributos se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5a571-p116">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>
  
<span data-ttu-id="5a571-171">**Atributos del elemento sender**</span><span class="sxs-lookup"><span data-stu-id="5a571-171">**Sender Element Attributes**</span></span>

|<span data-ttu-id="5a571-172">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="5a571-172">**Attribute**</span></span>|<span data-ttu-id="5a571-173">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a571-173">**Description**</span></span>|<span data-ttu-id="5a571-174">**Necesario/opcional**</span><span class="sxs-lookup"><span data-stu-id="5a571-174">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a571-175">Username</span><span class="sxs-lookup"><span data-stu-id="5a571-175">Username</span></span>  <br/> |<span data-ttu-id="5a571-176">El nombre del remitente.</span><span class="sxs-lookup"><span data-stu-id="5a571-176">The name of the sender.</span></span>  <br/> |<span data-ttu-id="5a571-177">Opcional</span><span class="sxs-lookup"><span data-stu-id="5a571-177">Optional</span></span>  <br/> |
|<span data-ttu-id="5a571-178">ID</span><span class="sxs-lookup"><span data-stu-id="5a571-178">ID</span></span>  <br/> |<span data-ttu-id="5a571-179">Identificador único de. la dirección del remitente</span><span class="sxs-lookup"><span data-stu-id="5a571-179">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="5a571-180">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5a571-180">Required</span></span>  <br/> |
|<span data-ttu-id="5a571-181">Email</span><span class="sxs-lookup"><span data-stu-id="5a571-181">Email</span></span>  <br/> |<span data-ttu-id="5a571-182">Dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="5a571-182">The sender's email address.</span></span>  <br/> |<span data-ttu-id="5a571-183">Opcional</span><span class="sxs-lookup"><span data-stu-id="5a571-183">Optional</span></span>  <br/> |
|<span data-ttu-id="5a571-184">Internal</span><span class="sxs-lookup"><span data-stu-id="5a571-184">Internal</span></span>  <br/> |<span data-ttu-id="5a571-p117">Determina si el usuario es un usuario interno o un usuario federado. Si el valor está establecido en True, el usuario es interno.</span><span class="sxs-lookup"><span data-stu-id="5a571-p117">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="5a571-187">Opcional</span><span class="sxs-lookup"><span data-stu-id="5a571-187">Optional</span></span>  <br/> |
|<span data-ttu-id="5a571-188">URI</span><span class="sxs-lookup"><span data-stu-id="5a571-188">Uri</span></span>  <br/> |<span data-ttu-id="5a571-189">URI de SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="5a571-189">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="5a571-190"> Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5a571-190">Required</span></span>  <br/> |
   
<span data-ttu-id="5a571-191">Los siguientes ejemplos muestran a los tipos de mensaje que puede contener el elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="5a571-191">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="5a571-192">Contiene ejemplos también de la forma en la que se usa cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5a571-192">It also provides examples of how each element is used.</span></span>
  
<span data-ttu-id="5a571-193">JOIN - un usuario se une a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5a571-193">Join - A user joins a chat room.</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="5a571-194">Elemento - un usuario sale de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5a571-194">Part - A user leaves a chat room.</span></span>
  
```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="5a571-195">Chat - dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="5a571-195">Chat - The sender's email address.</span></span>
  
```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="5a571-196">Backchat - un usuario solicita contenido desde el historial de chat.</span><span class="sxs-lookup"><span data-stu-id="5a571-196">Backchat - A user requests content from chat history.</span></span>
  
```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="5a571-197">Carga de archivos - un usuario carga un archivo.</span><span class="sxs-lookup"><span data-stu-id="5a571-197">File upload - A user uploads a file.</span></span>
  
```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="5a571-198">Descarga de archivos - un usuario descarga un archivo.</span><span class="sxs-lookup"><span data-stu-id="5a571-198">File download - A user downloads a file.</span></span>
  
```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="5a571-199">XSD de salida de Chat en grupo predeterminado y transformación XSL de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a571-199">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="5a571-200">El siguiente ejemplo de código muestra el resultado predeterminado del Servidor de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="5a571-200">The following code sample contains the default output from the Compliance Server:</span></span>
  
```
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

<span data-ttu-id="5a571-201">El siguiente ejemplo de código contiene un ejemplo de transformación XSL:</span><span class="sxs-lookup"><span data-stu-id="5a571-201">The following code sample contains a sample XSL transform:</span></span>
  
```
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