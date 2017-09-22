---
title: "Introducción a Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Conozca Microsoft Teams, su infraestructura y el uso de Office 365 con él."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 28be6a4565a783337b63e8dc4e7c1fddf9d743d9
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="363c0-103">Introducción a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="363c0-103">Overview of Microsoft Teams</span></span>
===========================

![Espacio de trabajo basado en chats en Office 365](media/Overview-Microsoft-Teams-image1.png)

<span data-ttu-id="363c0-p101">Microsoft Teams une todas las características de Office 365 para brindar un verdadero centro basado en chats para el trabajo en equipo y darles a los clientes la oportunidad de crear un entorno más abierto, fluido y digital. Microsoft Teams está construido a partir de tecnologías de Microsoft existentes que se entrelazan en Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="363c0-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="363c0-107">De forma predeterminada, Microsoft Teams aprovecha las identidades almacenadas en Azure Active Directory (Azure AD) y se integra con otros servicios de Office 365 para crear un sitio de SharePoint Online y una casilla de correo grupal de Exchange Online para cada equipo creado.</span><span class="sxs-lookup"><span data-stu-id="363c0-107">Out of the box, Microsoft Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="363c0-108">La función de chat persistente de Microsoft Teams se brinda a través de un servicio de chat que interactúa con el subestrato de Office 365, poniendo a disposición muchas de las funciones integradas de Office 365, como eDiscovery y archivado, a los datos que se van a intercambiar en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-108">Microsoft Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="363c0-p102">Microsoft Teams también brinda una experiencia de llamadas y reuniones integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.</span><span class="sxs-lookup"><span data-stu-id="363c0-p102">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="363c0-111">Para ampliar las funciones de Microsoft Teams, hay disponibles conectores, fichas y bots como [aplicaciones](https://go.microsoft.com/fwlink/?linkid=854629) para traer desde fuera información, contenido e interacciones de bots inteligentes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-111">To extend Microsoft Teams capabilities, Connectors, Tabs, and Bots are available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629) to bring external information, content, and intelligent bots’ interactions to Microsoft Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="363c0-112">Infraestructura de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="363c0-112">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="363c0-p103">Microsoft Teams está construido a partir de tecnologías de Microsoft existentes, que se entrelazan en Grupos de Office 365. Gracias a su tecnología de la nube de Microsoft, las organizaciones pueden esperar un excelente rendimiento y confiabilidad al aprovechar Microsoft Teams como parte de su historia de colaboración.</span><span class="sxs-lookup"><span data-stu-id="363c0-p103">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups. Powered by Microsoft’s cloud, organizations can expect excellent performance and reliability when leveraging Microsoft Teams as part of their collaboration story.</span></span>

<span data-ttu-id="363c0-p104">De manera predeterminada, un equipo creado en Microsoft Teams creará un grupo de Office 365 con el sitio de SharePoint Online completo con una biblioteca de documentos y una casilla de correo grupal de Exchange Online para el grupo, que Teams utilizará para almacenar información, como invitaciones a reuniones. Un equipo puede crearse a partir de grupos de Office 365 existentes, lo que permite que la pertenencia a grupos existente y el contenido almacenado en SharePoint Online y Exchange Online se traslade a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-p104">Out of the box, a team created in Microsoft Teams will create an Office 365 Group with the associated SharePoint Online site complete with a document library, an Exchange Online group mailbox for the Group which will be used by Teams to store information—such as meeting invites. A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Microsoft Teams.</span></span>

<span data-ttu-id="363c0-117">La función de chat persistente de Microsoft Teams se brinda a través de un servicio de chat que interactúa con el subestrato de Office 365, poniendo a disposición muchas de las funciones integradas de Office 365, como eDiscovery y archivado, a los datos que se van a intercambiar en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-117">Microsoft Teams persistent chat capability is provided by a Chat Service that interacts with Office 365 substrate, surfacing many of the built-in Office 365 capabilities such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="363c0-p105">Para complementar la función de Microsoft Teams como panel de chat persistente donde se llevan a cabo conversaciones informales en tiempo real sobre temas muy específicos o subgrupos específicos dentro del grupo, Teams también brinda una experiencia de reunión integrada en la infraestructura de próxima generación basada en la nube que también utilizan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.</span><span class="sxs-lookup"><span data-stu-id="363c0-p105">To complement Microsoft Teams capability as a persistent chat board where informal, real-time, conversations around very focused topics or specific sub-groups within the group take place, Teams also provides a meeting’s experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="363c0-120">Los grupos de Office 365 aprovechan las identidades almacenadas en Azure Active Directory (Azure AD) y, de esta manera, todas las funciones de autenticación y autorización en Azure AD, como admisión de autenticación multifactor (MFA), están disponibles para su uso en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), is readily available for use by Microsoft Teams.</span></span>

<span data-ttu-id="363c0-121">Para ampliar las funciones de Microsoft Teams, hay disponibles conectores, fichas y bots como aplicaciones para traer desde fuera información, contenido e interacciones de bots inteligentes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="363c0-121">To extend Microsoft Teams capabilities, Connectors, Tabs, and Bots are available as Apps to bring external information, contents, and intelligent bots interactions to Microsoft Teams.</span></span>

<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="363c0-122">Microsoft Teams y Office 365</span><span class="sxs-lookup"><span data-stu-id="363c0-122">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="363c0-p106">Los diferentes grupos tienen distintas necesidades en base a su función y estilo de trabajo. Office 365 está diseñado para el estilo de trabajo único de cada grupo e incluye aplicaciones integradas creadas para cada finalidad, como:</span><span class="sxs-lookup"><span data-stu-id="363c0-p106">Different groups have various needs based on their functional role and workstyle. Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, such as:</span></span>

-   <span data-ttu-id="363c0-125">Outlook para correos electrónicos empresariales, ahora con funcionalidad de grupos.</span><span class="sxs-lookup"><span data-stu-id="363c0-125">Outlook for enterprise-grade email, now with groups functionality.</span></span>

-   <span data-ttu-id="363c0-126">SharePoint para sitios y portales, servicios de contenido inteligente, automatización de procesos de negocio y Enterprise Search.</span><span class="sxs-lookup"><span data-stu-id="363c0-126">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search.</span></span>

-   <span data-ttu-id="363c0-127">Yammer para impulsar las conexiones dentro de toda la empresa</span><span class="sxs-lookup"><span data-stu-id="363c0-127">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="363c0-128">Skype Empresarial como la columna vertebral del audio y el vídeo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="363c0-128">Skype for Business as the backbone for enterprise voice and video.</span></span>

-   <span data-ttu-id="363c0-129">Y ahora, Microsoft Teams, el nuevo espacio de trabajo basado en chats de Office 365.</span><span class="sxs-lookup"><span data-stu-id="363c0-129">And now, Microsoft Teams, the new chat-based workspace in Office 365.</span></span>

<span data-ttu-id="363c0-p107">He aquí los casos de uso comunes para cada aplicación en Office 365. Para obtener instrucciones de uso detalladas, visite la [biblioteca de productividad de FastTrack](https://go.microsoft.com/fwlink/?linkid=854630)</span><span class="sxs-lookup"><span data-stu-id="363c0-p107">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="363c0-132">Aprovechado por usuarios y equipos que desean colaborar en tiempo real con el mismo grupo de personas.</span><span class="sxs-lookup"><span data-stu-id="363c0-132">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="363c0-133">Ayuda a los equipos a iterar rápidamente en un proyecto, a la vez que comparten archivos y colaboran en entregas compartidas.</span><span class="sxs-lookup"><span data-stu-id="363c0-133">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="363c0-134">Permite a los usuarios conectar una amplia gama de herramientas en su espacio de trabajo (como Planner, Power BI, GitHub, etc.).</span><span class="sxs-lookup"><span data-stu-id="363c0-134">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="363c0-135">Aprovechado por usuarios que prefieren colaborar en el entorno familiar del correo electrónico o de un modo más formal y estructurado.</span><span class="sxs-lookup"><span data-stu-id="363c0-135">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="363c0-136">Brinda procesos de negocio específicos que requieren el uso del correo electrónico para transmitir documentos e información dentro o fuera de los límites corporativos.</span><span class="sxs-lookup"><span data-stu-id="363c0-136">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="363c0-137">Se comunica y conecta con usuarios que se encuentran fuera de los grupos de trabajo u organizaciones inmediatos.</span><span class="sxs-lookup"><span data-stu-id="363c0-137">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="363c0-138">Aprovechado para ayudar a conectar a los usuarios de toda la empresa, para que se organicen en comunidades de práctica y compartan procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="363c0-138">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="363c0-139">Mejora los flujos de trabajo multidisciplinarios a través de una plataforma basada en fuentes, abierta y transparente.</span><span class="sxs-lookup"><span data-stu-id="363c0-139">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="363c0-140">Fomenta la relación entre ejecutivos y empleados con las conversaciones bidireccionales entre los líderes y la base más amplia de empleados.</span><span class="sxs-lookup"><span data-stu-id="363c0-140">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="363c0-141">Motiva a la fuerza de trabajo de primera línea a compartir y recibir conocimientos y experiencia.</span><span class="sxs-lookup"><span data-stu-id="363c0-141">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="363c0-142">Aprovechado para comunicación y colaboración en tiempo real, tanto de manera interna como externa con clientes/socios.</span><span class="sxs-lookup"><span data-stu-id="363c0-142">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="363c0-143">Permite realizar reuniones con audio, vídeo y contenido con pequeños o grandes grupos (incluidos foros con hasta 10 000 participantes).</span><span class="sxs-lookup"><span data-stu-id="363c0-143">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="363c0-144">Ofrece funcionalidad de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="363c0-144">Offers enterprise telephony functionality.</span></span>

-   <span data-ttu-id="363c0-145">Vea [Interacción entre Skype Empresarial y Microsoft Teams](Understand_how_Skype_for_Business_and_Microsoft_Teams_interact.md)</span><span class="sxs-lookup"><span data-stu-id="363c0-145">[How Skype for Business and Microsoft Teams interact](Understand_how_Skype_for_Business_and_Microsoft_Teams_interact.md)</span></span>

![](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="363c0-146">Aprovechado para sitios y portales (por ejemplo, anuncios y novedades de la empresa, búsquedas y colaboración en documentos).</span><span class="sxs-lookup"><span data-stu-id="363c0-146">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="363c0-147">Implementa automatización de procesos de negocio en bibliotecas de documentos y listas de información mediante la integración de Microsoft Flow y PowerApps.</span><span class="sxs-lookup"><span data-stu-id="363c0-147">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="363c0-148">Sitio de equipo de SharePoint con todo el poder, aprovisionado automáticamente para cada equipo de Microsoft para almacenamiento de archivos, novedades del equipo, páginas, listas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="363c0-148">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="363c0-149">Vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams.md)</span><span class="sxs-lookup"><span data-stu-id="363c0-149">[How SharePoint Online and OneDrive for Business interact with Microsoft Teams](Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams.md)</span></span>
