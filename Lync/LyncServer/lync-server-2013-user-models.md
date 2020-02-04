---
title: 'Lync Server 2013: modelos de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f45b3ea11911ea7a3dce36b0b6a9d64ac1e690
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="052d7-102">Modelos de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d7-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="052d7-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="052d7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="052d7-104">Los modelos de usuario descritos aquí proporcionan la base para las medidas de planeación de capacidad y las recomendaciones descritas en [planificación de capacidad para Lync Server 2013 con los modelos de usuario](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="052d7-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="052d7-105">Modelos de usuario de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d7-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="052d7-106">En la siguiente tabla se describe el modelo de usuario para registro, contactos, mensajería instantánea (mi) y presencia de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="052d7-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="052d7-107">Modelo de usuario de registro y entorno</span><span class="sxs-lookup"><span data-stu-id="052d7-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-108">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-108">Category</span></span></th>
<th><span data-ttu-id="052d7-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-110">Tamaño de implementación y distribución</span><span class="sxs-lookup"><span data-stu-id="052d7-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-111">Se modela una implementación de gran tamaño con tres sitios centrales y un grupo de servidores front-end por sitio.</span><span class="sxs-lookup"><span data-stu-id="052d7-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-112">Porcentaje de usuarios de Active Directory</span><span class="sxs-lookup"><span data-stu-id="052d7-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="052d7-113">Damos por hecho que el 70% de todos los usuarios de Active Directory de la organización está habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="052d7-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="052d7-114">80% de los usuarios habilitados han iniciado sesión en Lync Server cada día (80% de simultaneidad).</span><span class="sxs-lookup"><span data-stu-id="052d7-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="052d7-115">Los usuarios simultáneos constituyen la base de los cálculos para el resto de esta sección.</span><span class="sxs-lookup"><span data-stu-id="052d7-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-116">Cambios de Active Directory</span><span class="sxs-lookup"><span data-stu-id="052d7-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="052d7-117">Damos por hecho que el 0,5% del total de usuarios se crea y habilita para Lync en Active Directory cada semana y que el 0,5% del total de usuarios está deshabilitado de Active Directory y de Lync cada semana.</span><span class="sxs-lookup"><span data-stu-id="052d7-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="052d7-118">el 5% de los usuarios tiene al menos un atributo de Active Directory cambiado cada semana.</span><span class="sxs-lookup"><span data-stu-id="052d7-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-119">Grupos de distribución de Active Directory</span><span class="sxs-lookup"><span data-stu-id="052d7-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="052d7-120">Damos por hecho que el número de grupos de distribución de Active Directory en la organización es igual a tres veces el número de todos los usuarios de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="052d7-120">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory.</span></span> <span data-ttu-id="052d7-121">Los grupos de distribución tienen los tamaños siguientes:</span><span class="sxs-lookup"><span data-stu-id="052d7-121">The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-122">El 64 % tiene de 2 a 30 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="052d7-123">El 13 % tiene de 31 a 50 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="052d7-124">El 10 % tiene de 51 a 100 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="052d7-125">El 13 % tiene de 101 a 500 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-126">Usuarios de voz sobre IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="052d7-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="052d7-127">60% de los usuarios de Lync Server están habilitados para las comunicaciones unificadas (es decir, sus números de teléfono son propiedad de Lync Server).</span><span class="sxs-lookup"><span data-stu-id="052d7-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-128">Distribución de clientes registrados</span><span class="sxs-lookup"><span data-stu-id="052d7-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-129">65% de los clientes ejecutan el software Lync 2013, incluido Lync y Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="052d7-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="052d7-130">30% de los clientes que ejecutan software cliente de una versión anterior de Lync.</span><span class="sxs-lookup"><span data-stu-id="052d7-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="052d7-131">5% de los clientes que usan Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="052d7-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="052d7-p104">Si la movilidad está habilitada, se supone que el 40 % de los usuarios está usando la movilidad al mismo tiempo que las otras opciones de cliente registradas mencionadas anteriormente. En este caso, la relación de varios puntos de presencia (MPOP) del cliente es de 1:1,9. Si la movilidad está deshabilitada, la relación de MPOP será de 1:1,5.</span><span class="sxs-lookup"><span data-stu-id="052d7-p104">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options. In this case the client multiple point of presence (MPOP) ratio is 1:1.9. If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-135">Distribución de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="052d7-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-136">El 70 % de los usuarios se conecta internamente.</span><span class="sxs-lookup"><span data-stu-id="052d7-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="052d7-137">el 30% de los usuarios se conectan a través de un servidor perimetral y un director.</span><span class="sxs-lookup"><span data-stu-id="052d7-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-138">Distribución de contactos</span><span class="sxs-lookup"><span data-stu-id="052d7-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-p105">El número máximo de contactos que tiene un usuario es de 1.000. Menos del 1 % de los usuarios tiene 1.000 contactos. Menos del 25 % de los usuarios tiene 100 o más contactos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="052d7-p106">Una media de 80 contactos para los usuarios con conectividad en la nube pública. De estos usuarios:</span><span class="sxs-lookup"><span data-stu-id="052d7-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-p107">El 50% de los contactos está dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.</span><span class="sxs-lookup"><span data-stu-id="052d7-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="052d7-146">40% de los contactos son usuarios de la nube pública (como usuarios de AOL, Yahoo!, MSN o Google Talk).</span><span class="sxs-lookup"><span data-stu-id="052d7-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="052d7-147">El 10% de los contactos corresponde a socios federados.</span><span class="sxs-lookup"><span data-stu-id="052d7-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="052d7-148">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="052d7-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="052d7-149">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="052d7-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="052d7-150">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="052d7-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="052d7-151">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="052d7-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="052d7-152">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="052d7-152">has been announced.</span></span> <span data-ttu-id="052d7-153">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="052d7-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="052d7-154">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="052d7-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="052d7-155">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="052d7-155">Messenger.</span></span> <span data-ttu-id="052d7-156">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="052d7-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="052d7-157">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="052d7-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="052d7-158">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="052d7-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="052d7-159">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="052d7-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="052d7-p111">Una media de 50 contactos para los usuarios sin conectividad en la nube pública. De estos usuarios:</span><span class="sxs-lookup"><span data-stu-id="052d7-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-p112">El 80 % de los contactos está dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.</span><span class="sxs-lookup"><span data-stu-id="052d7-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="052d7-164">El 20 % de los contactos corresponde a socios federados.</span><span class="sxs-lookup"><span data-stu-id="052d7-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="052d7-p113">Cada usuario tiene un grupo de distribución en su lista de contactos. Para las pruebas de rendimiento, se supone que los grupos de distribución son siempre expandidos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="052d7-167">25% de los contactos de un usuario utilizan XMPP.</span><span class="sxs-lookup"><span data-stu-id="052d7-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-168">Tiempo de la sesión</span><span class="sxs-lookup"><span data-stu-id="052d7-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="052d7-p114">La sesión de inicio media de un usuario dura doce horas. Todos los usuarios inician sesión durante los primeros 120 minutos tras el inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="052d7-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="052d7-171">Modelo de usuario de presencia y MI</span><span class="sxs-lookup"><span data-stu-id="052d7-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-172">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-172">Category</span></span></th>
<th><span data-ttu-id="052d7-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-174">Sesiones de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="052d7-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="052d7-175">Cada usuario mantiene una media diaria de seis sesiones de MI de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="052d7-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="052d7-176">Diez mensajes instantáneos por sesión.</span><span class="sxs-lookup"><span data-stu-id="052d7-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="052d7-177">Cada mensaje coincide con dos mensajes de información SIP y dos mensajes SIP 200 OK (para los indicadores de estado como "&lt;el nombre&gt; está escribiendo")</span><span class="sxs-lookup"><span data-stu-id="052d7-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-178">Sondeo de presencia</span><span class="sxs-lookup"><span data-stu-id="052d7-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="052d7-p115">En términos generales, se supone que los sondeos de presencia tienen unos 60 sondeos de media por usuario y hora. Para cada usuario, se supone una media de:</span><span class="sxs-lookup"><span data-stu-id="052d7-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-p116">Un sondeo por día de la presencia de usuarios en la pestaña de organización de los usuarios (pero no en la de Lista de contactos). La media de no contactos en la pestaña de organización de los usuarios es de 15 usuarios. Dos operaciones de ver tarjetas de contacto al día.</span><span class="sxs-lookup"><span data-stu-id="052d7-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="052d7-184">Un sondeo de presencia cada vez que un usuario hace clic en otro usuario para iniciar una conversación, estimado en una vez por hora.</span><span class="sxs-lookup"><span data-stu-id="052d7-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="052d7-p117">Seis búsquedas de usuario por hora. Cada vez que se realiza una búsqueda, se envía un sondeo por lotes para cada usuario de la lista de resultados de la búsqueda. Se supone que el tamaño medio de los resultados de la búsqueda es de 20. Si los resultados de la búsqueda permanecen en pantalla, el sondeo por lotes se actualiza cada 5 minutos. Se supone que habrá dos actualizaciones por hora.</span><span class="sxs-lookup"><span data-stu-id="052d7-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="052d7-189">Cuando un usuario abre u obtiene la vista previa de un mensaje de correo en Outlook, un sondeo de la presencia de los usuarios en los campos Para: y CC: del mensaje, estimado en cinco mensajes por hora y cuatro usuarios por mensaje.</span><span class="sxs-lookup"><span data-stu-id="052d7-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-190">Suscripciones de presencia</span><span class="sxs-lookup"><span data-stu-id="052d7-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="052d7-p118">Cuando un usuario agrega a otro como contacto, el primer usuario se <em>suscribe</em> a cinco categorías de información sobre el segundo usuario. Las actualizaciones de estas categorías de información se envían automáticamente al primer usuario.</span><span class="sxs-lookup"><span data-stu-id="052d7-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="052d7-193">Para cada cliente, se envía una única petición de suscripción por lotes para obtener el estado de presencia de una media de 40 contactos, con 40 diálogos adicionales para obtener la presencia de los contactos federados.</span><span class="sxs-lookup"><span data-stu-id="052d7-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="052d7-194">La presencia de los miembros de un grupo de distribución expandido se averigua a través de las suscripciones de presencia persistente, y no a través de los sondeos, y se modela como 1 expansión por usuario durante cada 2 horas.</span><span class="sxs-lookup"><span data-stu-id="052d7-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="052d7-p119">Las <em>suscripciones breves</em> se producen cuando un usuario inicia sesión, se realiza una suscripción por lotes para todos los contactos del usuario y, después, el usuario se desconecta en un breve período. Se asumen 6 suscripciones breves por usuario y hora, donde cada suscripción tiene una duración de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-197">Publicación de presencia</span><span class="sxs-lookup"><span data-stu-id="052d7-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="052d7-198">El estado de presencia se publica a una media de 4 publicaciones por usuario y hora, con un máximo de 6 por usuario y hora.</span><span class="sxs-lookup"><span data-stu-id="052d7-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-199">Tamaño del documento de presencia</span><span class="sxs-lookup"><span data-stu-id="052d7-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="052d7-200">Se supone que el tamaño medio de un documento de presencia completo es de 4 K (de 25 K como máximo).</span><span class="sxs-lookup"><span data-stu-id="052d7-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-201">En la tabla siguiente se describe el modelo de usuario para el uso de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="052d7-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="052d7-202">Modelo de usuario para el uso de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="052d7-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-203">Modo de búsqueda de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="052d7-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="052d7-204">Uso</span><span class="sxs-lookup"><span data-stu-id="052d7-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-205">Solo consulta web de la libreta de direcciones (todas las consultas realizadas por el servicio de consulta web de la libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="052d7-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="052d7-206">Cuatro consultas de prefijo por usuario y día.</span><span class="sxs-lookup"><span data-stu-id="052d7-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="052d7-p120">60 consultas de búsqueda exactas por usuario y día. El 40 % de estas consultas se procesa por lotes, con una media de 20 contactos por consulta. El 60 % restante de las consultas es para un solo contacto.</span><span class="sxs-lookup"><span data-stu-id="052d7-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="052d7-p121">25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la otra es una consulta por lotes con una media de 20 contactos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="052d7-212">Una consulta de búsqueda de organización total por usuario y día.</span><span class="sxs-lookup"><span data-stu-id="052d7-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-p122">Modo mixto, se usa el archivo de la libreta de direcciones y las consultas web. Este es el modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="052d7-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="052d7-215">Solo dos tipos de consultas van a la red, las consultas de fotografía y de búsqueda de organización total.</span><span class="sxs-lookup"><span data-stu-id="052d7-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="052d7-p123">25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la otra es una consulta por lotes con una media de 20 contactos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="052d7-218">Una consulta de búsqueda de organización total por usuario y día.</span><span class="sxs-lookup"><span data-stu-id="052d7-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-219">En la siguiente tabla se describe el modelo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="052d7-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="052d7-220">Modelo de conferencia</span><span class="sxs-lookup"><span data-stu-id="052d7-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-221">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-221">Category</span></span></th>
<th><span data-ttu-id="052d7-222">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-223">Reuniones programadas &quot;y reunirse&quot; ahora con reuniones</span><span class="sxs-lookup"><span data-stu-id="052d7-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="052d7-224">60 % programadas, 40 % no programadas.</span><span class="sxs-lookup"><span data-stu-id="052d7-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="052d7-225">De las reuniones programadas, damos por hecho que 80% son conferencias asignadas, que son repeticiones de conferencias recurrentes; 10% son reuniones abiertas una vez. 8% son reuniones anónimas individuales y 2% son reuniones que se han cerrado una sola vez.</span><span class="sxs-lookup"><span data-stu-id="052d7-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-226">Distribución de clientes de conferencia</span><span class="sxs-lookup"><span data-stu-id="052d7-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-227">Para reuniones programadas:</span><span class="sxs-lookup"><span data-stu-id="052d7-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-228">65% de los usuarios de la Conferencia usan Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="052d7-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="052d7-229">5% de los usuarios de la Conferencia usan Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="052d7-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="052d7-230">el 30% de los usuarios de las conferencias usan clientes anteriores, entre los que se incluyen Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 y Microsoft Office Communicator Web Access (versión 2007).</span><span class="sxs-lookup"><span data-stu-id="052d7-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="052d7-231">Para reuniones no programadas:</span><span class="sxs-lookup"><span data-stu-id="052d7-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="052d7-232">70% de los usuarios de la Conferencia usan Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="052d7-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="052d7-233">el 30% de los usuarios de las conferencias usan clientes anteriores, entre los que se incluyen Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 y Microsoft Office Communicator Web Access (versión 2007).</span><span class="sxs-lookup"><span data-stu-id="052d7-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-234">Concurrencia en reuniones</span><span class="sxs-lookup"><span data-stu-id="052d7-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="052d7-p124">El 5 % de los usuarios asistirá a conferencias durante el horario de trabajo. Por tanto, en un grupo de 80.000 usuarios, hasta 4.000 usuarios pueden asistir a conferencias en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="052d7-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-237">Distribución de audio en las reuniones</span><span class="sxs-lookup"><span data-stu-id="052d7-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-238">El 40 % combinó el audio por VoIP y la conferencia de acceso telefónico local, con una relación 3 usuarios de VoIP por 1 usuario de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="052d7-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="052d7-239">El 35 % usó solo audio por VoIP.</span><span class="sxs-lookup"><span data-stu-id="052d7-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="052d7-240">El 15 % usó solo audioconferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="052d7-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="052d7-241">El 10 % no usó audio (conferencias solo de mensajería instantánea, con una media de cinco mensajes enviados por usuario).</span><span class="sxs-lookup"><span data-stu-id="052d7-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-242">Combinación de medios para conferencias</span><span class="sxs-lookup"><span data-stu-id="052d7-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="052d7-243">El 75 % de las conferencias son conferencias web, con audio más otras modalidades de colaboración.</span><span class="sxs-lookup"><span data-stu-id="052d7-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="052d7-244">Para estas conferencias, los otros métodos de colaboración son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="052d7-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="052d7-245">Estas cifras suman más del 100 % porque una conferencia puede tener varios métodos de colaboración.</span><span class="sxs-lookup"><span data-stu-id="052d7-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="052d7-p125">El 50 % agrega el uso compartido de aplicaciones. Se supone que un usuario envía datos a una velocidad pico de 1,1 MB por segundo.</span><span class="sxs-lookup"><span data-stu-id="052d7-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="052d7-248">El 50 % agrega mensajería instantánea (dos mensajes de media por usuario).</span><span class="sxs-lookup"><span data-stu-id="052d7-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="052d7-p126">El 20 % agrega colaboración de datos, incluidos PowerPoint o la pizarra. Entre estos, una media de dos archivos de PowerPoint presentados por conferencia, con un tamaño medio de archivo de PowerPoint de 10 MB (sin vídeo integrado), o de 30 MB (con vídeo integrado). Una media de 20 anotaciones por pizarra.</span><span class="sxs-lookup"><span data-stu-id="052d7-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="052d7-p127">El 20 % agrega vídeo. De estos usuarios, el 70 % está en conferencias habilitadas para vídeo de vista múltiple, en las que cada usuario recibe de 2 a 3 secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="052d7-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="052d7-253">El 15 % agrega notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="052d7-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-254">Distribución de los participantes en las reuniones</span><span class="sxs-lookup"><span data-stu-id="052d7-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-255">El 50 % corresponde a usuarios internos autenticados.</span><span class="sxs-lookup"><span data-stu-id="052d7-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="052d7-256">El 25 % corresponde a usuarios remotos autenticados.</span><span class="sxs-lookup"><span data-stu-id="052d7-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="052d7-257">El 15 % corresponde a usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="052d7-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="052d7-258">El 10% corresponde a usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="052d7-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-259">Distribución de participación en las reuniones</span><span class="sxs-lookup"><span data-stu-id="052d7-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="052d7-260">Se simula que los usuarios se unen a la reunión durante los primeros 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="052d7-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-261">En las agrupaciones de front-end normales, Lync Server 2013 tiene un tamaño máximo de reunión admitido de 250 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="052d7-262">Cada grupo puede hospedar una reunión de 250 usuarios de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="052d7-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="052d7-263">Mientras se produce una reunión de gran tamaño, el grupo también puede hospedar otras conferencias más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="052d7-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="052d7-264">Además, se admiten reuniones de hasta 1000 usuarios si se configura un grupo dedicado para hospedar estas reuniones.</span><span class="sxs-lookup"><span data-stu-id="052d7-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="052d7-265">Para obtener más información, consulte [compatibilidad con reuniones grandes en Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="052d7-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="052d7-266">Las conferencias se simularon del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="052d7-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="052d7-267">El 85 % de las conferencias contó con cuatro participantes.</span><span class="sxs-lookup"><span data-stu-id="052d7-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="052d7-268">El 10 % de las conferencias contó con seis participantes.</span><span class="sxs-lookup"><span data-stu-id="052d7-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="052d7-269">El 5 % de las conferencias contó con 11 participantes.</span><span class="sxs-lookup"><span data-stu-id="052d7-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="052d7-270">Hubo una gran conferencia con 250 usuarios.</span><span class="sxs-lookup"><span data-stu-id="052d7-270">One large conference of 250 users.</span></span>

<span data-ttu-id="052d7-271">En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para conferencias que incluye a usuarios de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="052d7-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="052d7-272">Modelo de usuario de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="052d7-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-273">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-273">Category</span></span></th>
<th><span data-ttu-id="052d7-274">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-275">Autenticados/Anónimos</span><span class="sxs-lookup"><span data-stu-id="052d7-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="052d7-p129">El 70 % de los autores de llamadas se une como anónimo y se le solicita un nombre registrado. El 30 % se une como usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="052d7-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-278">Duración de la llamada y música en espera</span><span class="sxs-lookup"><span data-stu-id="052d7-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="052d7-279">Duración media de llamada sin música en espera: 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="052d7-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="052d7-280">El 50 % de los usuarios que llaman escucha música en espera durante una media de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="052d7-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="052d7-281">Tono de marcado de frecuencia múltiple (DTMF)</span><span class="sxs-lookup"><span data-stu-id="052d7-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="052d7-p130">El 15 % de las conferencias de acceso telefónico local solo tiene coordinadores de teléfono. El 10 % de las conferencias mixtas que incluyen a usuarios de acceso telefónico local también tiene coordinadores de teléfono.</span><span class="sxs-lookup"><span data-stu-id="052d7-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="052d7-284">El 20 % de los coordinadores de teléfono usa dos comandos DTMF por conferencia.</span><span class="sxs-lookup"><span data-stu-id="052d7-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-285">Idiomas del anuncio</span><span class="sxs-lookup"><span data-stu-id="052d7-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="052d7-286">En las simulaciones se usa inglés como idioma del anuncio.</span><span class="sxs-lookup"><span data-stu-id="052d7-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-287">En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para salas de espera de conferencia.</span><span class="sxs-lookup"><span data-stu-id="052d7-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="052d7-288">Modelo de usuario para salas de espera de conferencia</span><span class="sxs-lookup"><span data-stu-id="052d7-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-289">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-289">Category</span></span></th>
<th><span data-ttu-id="052d7-290">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-291">Número de usuarios en sala de espera</span><span class="sxs-lookup"><span data-stu-id="052d7-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="052d7-292">El 5 % de los usuarios de acceso telefónico local pasa por la sala de espera y el 25 % de otros usuarios también.</span><span class="sxs-lookup"><span data-stu-id="052d7-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-293">Admisión desde la sala de espera</span><span class="sxs-lookup"><span data-stu-id="052d7-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="052d7-294">En las simulaciones, el moderador admitió a todos los usuarios antes de que transcurriera el tiempo de espera de cliente.</span><span class="sxs-lookup"><span data-stu-id="052d7-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-295">En la tabla siguiente se describe el modelo de usuario para otras sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="052d7-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="052d7-296">Modelo de usuario para sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="052d7-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-297">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-297">Category</span></span></th>
<th><span data-ttu-id="052d7-298">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-299">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="052d7-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="052d7-300">Cada usuario participa en 5 sesiones de uso compartido de aplicaciones de punto a punto al mes, para una media de 0,25 sesiones al día.</span><span class="sxs-lookup"><span data-stu-id="052d7-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-301">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="052d7-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="052d7-p131">Cada usuario participa en 1 sesión de transferencia de archivos de punto a punto al mes (como parte de una sesión de MI), para una media de 0,05 sesiones al día. El tamaño de archivo medio transferido por sesión es de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="052d7-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="052d7-304">La siguiente tabla describe el modelo de usuario de las directivas.</span><span class="sxs-lookup"><span data-stu-id="052d7-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="052d7-305">Modelo de usuario de directivas</span><span class="sxs-lookup"><span data-stu-id="052d7-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="052d7-306">Categoría</span><span class="sxs-lookup"><span data-stu-id="052d7-306">Category</span></span></th>
<th><span data-ttu-id="052d7-307">Descripción</span><span class="sxs-lookup"><span data-stu-id="052d7-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="052d7-308">Conferencias, presencia y directivas de archivado</span><span class="sxs-lookup"><span data-stu-id="052d7-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="052d7-309">Se supone que hay una directiva global, 10 directivas de conferencia de etiqueta, 4 directivas de archivado y 10 directivas de presencia de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="052d7-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="052d7-310">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="052d7-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="052d7-311">Se supone que hay una directiva global y 2 directivas de etiqueta por sitio.</span><span class="sxs-lookup"><span data-stu-id="052d7-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="052d7-312">El 100 % de los sitios tiene una directiva de sitio y el 30 % de los usuarios tiene asignada una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="052d7-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="052d7-313">Se supone un plan de marcado por sitio y dos rutas por sitio.</span><span class="sxs-lookup"><span data-stu-id="052d7-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="052d7-314">Hora punta</span><span class="sxs-lookup"><span data-stu-id="052d7-314">Busy Hour</span></span>

<span data-ttu-id="052d7-p133">Para sesiones de punto a punto, la carga máxima se calcula con Intentos de llamada en hora punta (BHCA). Este término del sector de la voz presupone que el 50 % de todas las llamadas del día se realizará en el 20 % del tiempo. Se calcula con la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="052d7-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="052d7-318">Las pruebas de rendimiento han simulado hora punta ejecutando VoIP y otras sesiones de punto a punto en una carga de hora punta para al menos 1,6 horas por día.</span><span class="sxs-lookup"><span data-stu-id="052d7-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="052d7-p134">En la carga máxima de conferencia se supone que el 75 % de todas las conferencias para un día de ocho horas tiene lugar en cuatro horas punta. Estas horas punta tienen 1,5 veces la carga media de conferencia.</span><span class="sxs-lookup"><span data-stu-id="052d7-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="052d7-321">Llamadas de telefonía IP a RTC</span><span class="sxs-lookup"><span data-stu-id="052d7-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="052d7-322">En las llamadas de voz empresariales se aplican las siguientes hipótesis:</span><span class="sxs-lookup"><span data-stu-id="052d7-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="052d7-323">el 50% de los usuarios están habilitados para telefonía IP empresarial y 60% de estos usuarios están habilitados para las llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="052d7-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="052d7-p135">Cada uno de estos usuarios habilitados para las llamadas RTC realiza 4 llamadas RTC durante la hora punta. Cada llamada dura 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="052d7-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="052d7-326">El 65 % de estas llamadas de voz RTC usa desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="052d7-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="052d7-327">Movilidad</span><span class="sxs-lookup"><span data-stu-id="052d7-327">Mobility</span></span>

<span data-ttu-id="052d7-p136">Se supone que el 40 % de los usuarios registrados está habilitado para la movilidad. Para cada usuario que tiene la movilidad habilitada, se supone que la actividad del cliente móvil se suma a la de las demás instancias de MPOP para dicho usuario, salvo las interacciones de conferencia, para las que el cliente de movilidad es solo otro tipo de cliente que se puede usar para participar en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="052d7-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="052d7-330">Chat persistente</span><span class="sxs-lookup"><span data-stu-id="052d7-330">Persistent Chat</span></span>

<span data-ttu-id="052d7-331">Se supone que el 25 % de los usuarios registrado participará en sesiones de chat persistentes, con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="052d7-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="052d7-332">Una media de 1,5 salones de chat por usuario.</span><span class="sxs-lookup"><span data-stu-id="052d7-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="052d7-333">Cada salón de chat genera 12 peticiones de sondeo por hora, con una media de 10 destinatarios cada una.</span><span class="sxs-lookup"><span data-stu-id="052d7-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="052d7-334">Grupo de respuesta y estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="052d7-334">Response Group and Call Park</span></span>

<span data-ttu-id="052d7-p137">Se supone que el 0,15 % de los usuarios registrados pertenece a grupos de respuesta. Se supone que el 0,02 % de los usuarios registrados tiene llamadas estacionadas en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="052d7-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

