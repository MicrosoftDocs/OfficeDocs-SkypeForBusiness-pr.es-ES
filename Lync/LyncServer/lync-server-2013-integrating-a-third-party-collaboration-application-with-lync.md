---
title: Integración de una aplicación de colaboración de terceros con Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6210591be9aaf281b76ea02f6f919ea3d1620db7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="ae328-102">Integración de una aplicación de colaboración de terceros con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae328-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae328-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ae328-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ae328-104">Puede integrar Lync 2013 con cualquier aplicación de colaboración en línea de terceros agregando información sobre la aplicación al registro.</span><span class="sxs-lookup"><span data-stu-id="ae328-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="ae328-105">Puede usar Lync 2013 para iniciar sesiones de conferencia de datos hospedadas en un servidor interno, un servicio basado en Internet o ambos.</span><span class="sxs-lookup"><span data-stu-id="ae328-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="ae328-106">Las sesiones de colaboración o de conferencia de datos se pueden iniciar desde la lista de contactos o desde una sesión de mensajería instantánea, voz o vídeo existente.</span><span class="sxs-lookup"><span data-stu-id="ae328-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="ae328-107">Lync 2013 solo actúa como vehículo para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae328-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="ae328-108">Las conversaciones existentes de Lync 2013 permanecen activas una vez iniciada la sesión de colaboración en línea.</span><span class="sxs-lookup"><span data-stu-id="ae328-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="ae328-109">En las siguientes secciones se describe cómo integrar Lync 2013 con aplicaciones de colaboración basadas en Internet y en servidor.</span><span class="sxs-lookup"><span data-stu-id="ae328-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="ae328-110">Integración de una aplicación de colaboración basada en Internet con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ae328-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="ae328-111">En general, los pasos necesarios para integrar una aplicación de colaboración de otro fabricante son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae328-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="ae328-112">La información acerca de la aplicación se agrega al Registro.</span><span class="sxs-lookup"><span data-stu-id="ae328-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="ae328-113">El organizador inicia sesión en Lync 2013 y selecciona contactos para uso compartido y colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="ae328-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="ae328-114">Es posible también que el organizador ya esté participando en una conversación y decida agregar la conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="ae328-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="ae328-115">Lync 2013 lee el registro, inicia la aplicación de colaboración y, a continuación, envía un mensaje SIP personalizado (un appINVITE) a los participantes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="ae328-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="ae328-116">Los participantes aceptan la invitación y la aplicación de colaboración se inicia en el equipo de cada una de las personas.</span><span class="sxs-lookup"><span data-stu-id="ae328-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="ae328-117">Lync 2013 usa el registro para determinar la aplicación de colaboración que se va a usar y, a continuación, inicia esa aplicación con los parámetros incluidos en el mensaje appINVITE.</span><span class="sxs-lookup"><span data-stu-id="ae328-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="ae328-118">En la tabla siguiente se describen las entradas del registro necesarias para integrar una aplicación de colaboración basada en Internet con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ae328-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="ae328-119">Estas entradas se colocan en el registro en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="ae328-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="ae328-120">HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\de\\aplicaciones de Lync</span><span class="sxs-lookup"><span data-stu-id="ae328-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="ae328-121">Entradas del Registro para una aplicación de colaboración basada en Internet</span><span class="sxs-lookup"><span data-stu-id="ae328-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae328-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="ae328-122">Name</span></span></th>
<th><span data-ttu-id="ae328-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="ae328-123">Type</span></span></th>
<th><span data-ttu-id="ae328-124">Datos</span><span class="sxs-lookup"><span data-stu-id="ae328-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae328-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="ae328-125">Name</span></span></p></td>
<td><p><span data-ttu-id="ae328-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-127">El nombre de la aplicación para los menús de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ae328-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="ae328-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="ae328-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-130">Ruta de acceso al icono de 16 x 16 píxeles, BMP o PNG.</span><span class="sxs-lookup"><span data-stu-id="ae328-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae328-131">Path</span><span class="sxs-lookup"><span data-stu-id="ae328-131">Path</span></span></p></td>
<td><p><span data-ttu-id="ae328-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-133">Ruta de acceso de los participantes para iniciar la aplicación de colaboración en línea.</span><span class="sxs-lookup"><span data-stu-id="ae328-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="ae328-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="ae328-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-136">Ruta de acceso del organizador para iniciar la aplicación de colaboración en línea.</span><span class="sxs-lookup"><span data-stu-id="ae328-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="ae328-137">Esta ruta puede contener uno o varios parámetros personalizados definidos en la subclave Parameters.</span><span class="sxs-lookup"><span data-stu-id="ae328-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="ae328-138">Por ejemplo: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="ae328-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae328-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="ae328-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="ae328-140">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="ae328-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="ae328-p106">0 = Sesión local. La aplicación se inicia en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ae328-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="ae328-143">1 = Sesión entre dos participantes (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ae328-143">1 = Two-party session (default).</span></span> <span data-ttu-id="ae328-144">Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario.</span><span class="sxs-lookup"><span data-stu-id="ae328-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="ae328-145">El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ae328-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="ae328-146">2 = Sesión de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="ae328-146">2 = Multiparty session.</span></span> <span data-ttu-id="ae328-147">Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema a los demás usuarios, solicitándole que inicien la aplicación especificada en su propio equipo.</span><span class="sxs-lookup"><span data-stu-id="ae328-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="ae328-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="ae328-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-p109">Lista de menús en los que aparecerá este comando, separados con caracteres de punto y coma. Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ae328-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae328-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="ae328-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="ae328-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="ae328-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="ae328-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="ae328-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="ae328-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="ae328-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="ae328-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="ae328-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="ae328-157">Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="ae328-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ae328-158">En la siguiente tabla se describen las entradas del Registro para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae328-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="ae328-159">Estas entradas se colocan\_en\_el\\software\\de\\usuario\\actual\\de\\los\\parámetros\\de las aplicaciones de Lync SessionManager de Microsoft Office 15,0 Lync.</span><span class="sxs-lookup"><span data-stu-id="ae328-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="ae328-160">Entradas del Registro para una aplicación de colaboración basada en Internet</span><span class="sxs-lookup"><span data-stu-id="ae328-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae328-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="ae328-161">Name</span></span></th>
<th><span data-ttu-id="ae328-162">Tipo</span><span class="sxs-lookup"><span data-stu-id="ae328-162">Type</span></span></th>
<th><span data-ttu-id="ae328-163">Datos</span><span class="sxs-lookup"><span data-stu-id="ae328-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae328-164">Parámetro1</span><span class="sxs-lookup"><span data-stu-id="ae328-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="ae328-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-166">Se usa en formato con tokens (<code>%Parm1%</code>) para agregar valores específicos del usuario a la clave del registro OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="ae328-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-167">Parámetro2</span><span class="sxs-lookup"><span data-stu-id="ae328-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="ae328-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-169">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="ae328-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae328-170">Param3</span><span class="sxs-lookup"><span data-stu-id="ae328-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="ae328-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-172">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="ae328-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ae328-173">La siguiente configuración del registro de ejemplo integra el cliente de colaboración Adatum con Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="ae328-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="ae328-174">Integración de una aplicación de colaboración basada en servidor con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ae328-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="ae328-175">La configuración para agregar comandos para iniciar una aplicación de colaboración basada en servidor desde dentro de Lync 2013 es similar a la descrita en la sección anterior, lo que integra una aplicación de colaboración basada en Internet con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ae328-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="ae328-176">No obstante, el parámetro OriginatorPath no es necesario y algunos valores varían.</span><span class="sxs-lookup"><span data-stu-id="ae328-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="ae328-177">Las entradas del registro se colocan en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="ae328-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="ae328-178">HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\de\\aplicaciones de Lync</span><span class="sxs-lookup"><span data-stu-id="ae328-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="ae328-179">Entradas del Registro para una aplicación de colaboración basada en servidor</span><span class="sxs-lookup"><span data-stu-id="ae328-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae328-180">Nombre</span><span class="sxs-lookup"><span data-stu-id="ae328-180">Name</span></span></th>
<th><span data-ttu-id="ae328-181">Tipo</span><span class="sxs-lookup"><span data-stu-id="ae328-181">Type</span></span></th>
<th><span data-ttu-id="ae328-182">Datos</span><span class="sxs-lookup"><span data-stu-id="ae328-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae328-183">Nombre</span><span class="sxs-lookup"><span data-stu-id="ae328-183">Name</span></span></p></td>
<td><p><span data-ttu-id="ae328-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-185">Nombre de la aplicación tal como aparece en el menú.</span><span class="sxs-lookup"><span data-stu-id="ae328-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="ae328-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="ae328-187">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="ae328-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="ae328-188">Valor =1.</span><span class="sxs-lookup"><span data-stu-id="ae328-188">Value = 1.</span></span> <span data-ttu-id="ae328-189">Establece el tipo de aplicación en protocolo.</span><span class="sxs-lookup"><span data-stu-id="ae328-189">Sets the application type to protocol.</span></span> <span data-ttu-id="ae328-190">Los otros valores posibles no se aplican en este caso.</span><span class="sxs-lookup"><span data-stu-id="ae328-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="ae328-191">Si no está presente, ApplicationType se establece en 0 (ejecutable).</span><span class="sxs-lookup"><span data-stu-id="ae328-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae328-192">Path</span><span class="sxs-lookup"><span data-stu-id="ae328-192">Path</span></span></p></td>
<td><p><span data-ttu-id="ae328-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-194">Protocolo usado para iniciar la aplicación de colaboración.</span><span class="sxs-lookup"><span data-stu-id="ae328-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="ae328-195">Para Live Meeting 2007, el valor de path se establece en <code>meet:%conf-uri%</code>.</span><span class="sxs-lookup"><span data-stu-id="ae328-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="ae328-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="ae328-197">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="ae328-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="ae328-p114">0 = Sesión local. La aplicación se inicia en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ae328-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="ae328-200">1 = Sesión entre dos participantes (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ae328-200">1 = Two-party session (default).</span></span> <span data-ttu-id="ae328-201">Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario.</span><span class="sxs-lookup"><span data-stu-id="ae328-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="ae328-202">El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ae328-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="ae328-203">2 = Sesión de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="ae328-203">2 = Multiparty session.</span></span> <span data-ttu-id="ae328-204">Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema a los demás usuarios, solicitándole que inicien la aplicación especificada en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ae328-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae328-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="ae328-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="ae328-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-207">DATOS = El tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="ae328-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae328-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="ae328-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="ae328-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ae328-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ae328-210">Una lista de los menús en los que aparecerá este comando, separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="ae328-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="ae328-211">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ae328-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae328-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="ae328-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="ae328-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="ae328-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="ae328-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="ae328-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="ae328-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="ae328-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="ae328-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="ae328-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="ae328-217">Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="ae328-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ae328-218">En el siguiente ejemplo, se agregan comandos para iniciar el cliente de colaboración Adatum desde Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="ae328-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

