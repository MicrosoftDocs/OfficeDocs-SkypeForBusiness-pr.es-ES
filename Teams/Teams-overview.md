---
title: Introducción a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Conozca Microsoft Teams, su infraestructura y cómo funciona con Office 365.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbbd2cad0b84ccdcc887d5bcdf272c1556c9c546
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="37a4b-103">Introducción a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37a4b-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="37a4b-p101">Microsoft Teams une todas las características de Office 365 para brindar un verdadero centro basado en chats para el trabajo en equipo y darles a los clientes la oportunidad de crear un entorno más abierto, fluido y digital. Microsoft Teams está construido a partir de tecnologías de Microsoft existentes que se entrelazan en Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="37a4b-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="37a4b-106">De forma predeterminada, Microsoft Teams aprovecha las identidades almacenadas en Azure Active Directory (Azure AD) y se integra con otros servicios de Office 365 para crear un sitio de SharePoint Online y una casilla de correo grupal de Exchange Online para cada equipo creado.</span><span class="sxs-lookup"><span data-stu-id="37a4b-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="37a4b-107">Cualquier persona con una cuenta de correo electrónico empresariales o de clientes, como Outlook, Gmail u otros, puede participar como invitado en los equipos.</span><span class="sxs-lookup"><span data-stu-id="37a4b-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="37a4b-108">Todos los invitados en equipos están cubiertos por la misma conformidad y auditoría protección que el resto de Office 365 y los invitados pueden administrarse de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="37a4b-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="37a4b-109">Administradores pueden centralmente administrar cómo participan invitados dentro de su entorno de Office 365 y fácilmente ver, agregar o revocar el acceso de invitado a los inquilinos de host.</span><span class="sxs-lookup"><span data-stu-id="37a4b-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="37a4b-110">Teams proporciona una función de chat persistente, llamadas y reuniones, fácil acceso a otros componentes de Office 365 y una sólida historia de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="37a4b-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="37a4b-111">Todo ello crea un centro ideal para trabajar en equipo que se adecúa tanto a grandes empresas como pequeñas organizaciones y todos los que estén en medio.</span><span class="sxs-lookup"><span data-stu-id="37a4b-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="37a4b-112">Para ampliar las funcionalidades de Microsoft Teams, use conectores, fichas y bots (disponibles en forma de [aplicaciones](https://go.microsoft.com/fwlink/?linkid=854629)) para traer desde fuera información, contenido e interacciones de bots inteligentes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37a4b-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="37a4b-113">Infraestructura de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37a4b-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="37a4b-114">Microsoft Teams está construido a partir de tecnologías de Microsoft existentes, que se entrelazan en Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="37a4b-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="37a4b-115">Gracias a su tecnología de la nube de Microsoft, las organizaciones pueden esperar un excelente rendimiento y confiabilidad al aprovechar Microsoft Teams como parte de su historia de colaboración.</span><span class="sxs-lookup"><span data-stu-id="37a4b-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="37a4b-116">De manera predeterminada, un equipo creado en Microsoft Teams creará un grupo de Office 365, un sitio de SharePoint Online (completo con una biblioteca de documentos) y un buzón de Exchange Online para el grupo, que Microsoft Teams utilizará para almacenar información, como invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="37a4b-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="37a4b-117">Un equipo puede crearse a partir de grupos de Office 365 existentes, lo que permite que la pertenencia a grupos existente y el contenido almacenado en SharePoint Online y Exchange Online se traslade a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37a4b-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="37a4b-118">Para complementar la funcionalidad de Microsoft Teams como panel de chat persistente donde se llevan a cabo conversaciones informales en tiempo real, Microsoft Teams también brinda una experiencia de reunión integrada en la infraestructura de próxima generación basada en la nube que también utilizan Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="37a4b-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="37a4b-119">Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.</span><span class="sxs-lookup"><span data-stu-id="37a4b-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="37a4b-120">Los grupos de Office 365 aprovechan las identidades almacenadas en Azure Active Directory (Azure AD) y, de esta manera, todas las funcionalidades de autenticación y autorización en Azure AD, como admisión de autenticación multifactor (MFA), están disponibles para su uso en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37a4b-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

<span data-ttu-id="37a4b-121">Microsoft Teams también brinda una experiencia de llamadas y reuniones integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="37a4b-121">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="37a4b-122">Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.</span><span class="sxs-lookup"><span data-stu-id="37a4b-122">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

> [!NOTE]
> <span data-ttu-id="37a4b-123">En función de los comentarios de los clientes, nuevos grupos de 365 de Office genera como resultado de la creación de un equipo de Microsoft Teams no volverán a aparecer en Outlook de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37a4b-123">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="37a4b-124">Los clientes que desea continuar con el comportamiento existente de mostrar estos grupos en Outlook, se proporcionará un cmdlet de PowerShell en línea de Exchange que puede habilitar el grupo para la experiencia de Outlook.</span><span class="sxs-lookup"><span data-stu-id="37a4b-124">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="37a4b-125">Grupos creados a través de Outlook y se habilitó posteriormente para equipos continuará mostrando en Outlook y equipos.</span><span class="sxs-lookup"><span data-stu-id="37a4b-125">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="37a4b-126">Esta actualización se aumentará progresivamente roll out a través de Outlook y los equipos en los próximos meses.</span><span class="sxs-lookup"><span data-stu-id="37a4b-126">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="37a4b-127">Microsoft Teams y Office 365</span><span class="sxs-lookup"><span data-stu-id="37a4b-127">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="37a4b-128">Los diferentes grupos tienen distintas necesidades en base a su función y estilo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37a4b-128">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="37a4b-129">Office 365 está diseñado para el estilo de trabajo único de cada grupo e incluye aplicaciones integradas creadas para cada finalidad, como:</span><span class="sxs-lookup"><span data-stu-id="37a4b-129">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="37a4b-130">Outlook para correos electrónicos empresariales, ahora con funcionalidad de grupos.</span><span class="sxs-lookup"><span data-stu-id="37a4b-130">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="37a4b-131">SharePoint para sitios y portales, servicios de contenido inteligente, automatización de procesos de negocio y Enterprise Search.</span><span class="sxs-lookup"><span data-stu-id="37a4b-131">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="37a4b-132">Yammer para impulsar las conexiones dentro de toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="37a4b-132">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="37a4b-133">Skype Empresarial como la columna vertebral del audio y el vídeo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="37a4b-133">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="37a4b-134">Y ahora, Microsoft Teams, el nuevo espacio de trabajo basado en chats de Office 365.</span><span class="sxs-lookup"><span data-stu-id="37a4b-134">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="37a4b-p110">He aquí los casos de uso comunes para cada aplicación en Office 365. Para obtener instrucciones de uso detalladas, visite la [biblioteca de productividad de FastTrack](https://go.microsoft.com/fwlink/?linkid=854630)</span><span class="sxs-lookup"><span data-stu-id="37a4b-p110">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Icono de Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="37a4b-138">Aprovechado por usuarios y equipos que desean colaborar en tiempo real con el mismo grupo de personas.</span><span class="sxs-lookup"><span data-stu-id="37a4b-138">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="37a4b-139">Ayuda a los equipos a iterar rápidamente en un proyecto, a la vez que comparten archivos y colaboran en entregas compartidas.</span><span class="sxs-lookup"><span data-stu-id="37a4b-139">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="37a4b-140">Permite a los usuarios conectarse a una amplia gama de herramientas en su área de trabajo (como planificador, alimentación BI, GitHub, etcetera).</span><span class="sxs-lookup"><span data-stu-id="37a4b-140">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Icono de Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="37a4b-142">Aprovechado por usuarios que prefieren colaborar en el entorno familiar del correo electrónico o de un modo más formal y estructurado.</span><span class="sxs-lookup"><span data-stu-id="37a4b-142">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="37a4b-143">Brinda procesos de negocio específicos que requieren el uso del correo electrónico para transmitir documentos e información dentro o fuera de los límites corporativos.</span><span class="sxs-lookup"><span data-stu-id="37a4b-143">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="37a4b-144">Se comunica y conecta con usuarios que se encuentran fuera de los grupos de trabajo u organizaciones inmediatos.</span><span class="sxs-lookup"><span data-stu-id="37a4b-144">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Icono de Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="37a4b-146">Aprovechado para ayudar a conectar a los usuarios de toda la empresa, para que se organicen en comunidades de práctica y compartan procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="37a4b-146">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="37a4b-147">Mejora los flujos de trabajo multidisciplinarios a través de una plataforma basada en fuentes, abierta y transparente.</span><span class="sxs-lookup"><span data-stu-id="37a4b-147">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="37a4b-148">Fomenta la relación entre ejecutivos y empleados con las conversaciones bidireccionales entre los líderes y la base más amplia de empleados.</span><span class="sxs-lookup"><span data-stu-id="37a4b-148">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="37a4b-149">Motiva a la fuerza de trabajo de primera línea a compartir y recibir conocimientos y experiencia.</span><span class="sxs-lookup"><span data-stu-id="37a4b-149">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Icono de Skype Empresarial.](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="37a4b-151">Aprovechado para comunicación y colaboración en tiempo real, tanto de manera interna como externa con clientes/socios.</span><span class="sxs-lookup"><span data-stu-id="37a4b-151">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="37a4b-152">Permite realizar reuniones con audio, vídeo y contenido con pequeños o grandes grupos (incluidos foros con hasta 10 000 participantes).</span><span class="sxs-lookup"><span data-stu-id="37a4b-152">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="37a4b-153">Ofrece funcionalidad de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="37a4b-153">Offers enterprise telephony functionality.</span></span>


![Icono de Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="37a4b-155">Aprovechado para sitios y portales (por ejemplo, anuncios y novedades de la empresa, búsquedas y colaboración en documentos).</span><span class="sxs-lookup"><span data-stu-id="37a4b-155">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="37a4b-156">Implementa automatización de procesos de negocio en bibliotecas de documentos y listas de información mediante la integración de Microsoft Flow y PowerApps.</span><span class="sxs-lookup"><span data-stu-id="37a4b-156">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="37a4b-157">Sitio de equipo de SharePoint con todo el poder, aprovisionado automáticamente para cada equipo de Microsoft para almacenamiento de archivos, novedades del equipo, páginas, listas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="37a4b-157">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="37a4b-158">Vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="37a4b-158">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="37a4b-159">Problemas conocidos de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37a4b-159">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="37a4b-160">Notas de la versión del cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37a4b-160">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="37a4b-161">¿Qué ha pasado con las preguntas frecuentes del administrador de Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="37a4b-161">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="37a4b-162">Aunque las preguntas frecuentes del administrador de Microsoft Teams eran muy útiles cuando se publicó por primera vez Microsoft Teams, rápidamente se convirtieron en un "cajón desastre" donde era muy difícil encontrar algo.</span><span class="sxs-lookup"><span data-stu-id="37a4b-162">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="37a4b-163">Por ese motivo hemos decidido deshacernos de las preguntas frecuentes y hemos incorporado la información más relevante en la documentación de Microsoft Teams que está leyendo en este momento.</span><span class="sxs-lookup"><span data-stu-id="37a4b-163">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="37a4b-164">Aquí encontrará toda la información que estaba en las preguntas frecuentes, en su contexto correcto.</span><span class="sxs-lookup"><span data-stu-id="37a4b-164">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="37a4b-165">Si buscas algo que no puede encontrar aquí, por favor Díganos acerca de él en la sección **comentarios** a continuación.</span><span class="sxs-lookup"><span data-stu-id="37a4b-165">If you're looking for something that you can't find here, please tell us about it in the **Feedback** section below.</span></span> <span data-ttu-id="37a4b-166">Intentaremos responder a sus comentarios dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="37a4b-166">We try to respond to your feedback within 24 hours.</span></span>

<span data-ttu-id="37a4b-167">Por cierto, **sí que** hay una sección de preguntas frecuentes en el [recorrido desde Skype Empresarial a Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="37a4b-167">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
