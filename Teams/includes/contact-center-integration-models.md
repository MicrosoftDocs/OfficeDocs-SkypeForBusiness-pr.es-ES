## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="b471f-101">Modelos de integración para proveedores de soluciones</span><span class="sxs-lookup"><span data-stu-id="b471f-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="b471f-102">Como proveedor de soluciones de centro de contacto, hay tres modelos entre los que elegir para integrar la solución del centro de contacto conectado en Teams:</span><span class="sxs-lookup"><span data-stu-id="b471f-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="b471f-103">Si desea usar SBC certificados y Enrutamiento directo para conectar una solución de centro de contacto a Teams, vea el modelo [Conectar.](?tabs=connect#steps)</span><span class="sxs-lookup"><span data-stu-id="b471f-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="b471f-104">Si desea usar los bots de Azure y las API de comunicación de Microsoft Graph para permitir que los proveedores de soluciones creen aplicaciones de Teams, vea [el modelo Extender.](?tabs=extend#steps)</span><span class="sxs-lookup"><span data-stu-id="b471f-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="b471f-105">Si desea usar un SDK que permite a los proveedores de soluciones instalar experiencias nativas de Teams en su aplicación, vea [el modelo de Power.](?tabs=power#steps)</span><span class="sxs-lookup"><span data-stu-id="b471f-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="b471f-106">Las soluciones de Power serán posibles cuando el SDK esté disponible, hacia finales de 2021.</span><span class="sxs-lookup"><span data-stu-id="b471f-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="b471f-107">**El modelo Conectar**</span><span class="sxs-lookup"><span data-stu-id="b471f-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="b471f-108">El modelo Connect usa SBC certificados por Microsoft y Enrutamiento directo para conectar soluciones del centro de contactos a la infraestructura del sistema telefónico de Teams, lo que permite mejorar el enrutamiento, la configuración y la información del sistema.</span><span class="sxs-lookup"><span data-stu-id="b471f-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="b471f-109">Los agentes pueden configurar asistentes virtuales automatizados y colas de enrutamiento basadas en aptitudes para recopilar información y conectar a los clientes con expertos en la materia.</span><span class="sxs-lookup"><span data-stu-id="b471f-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="b471f-110">**Características destacadas:**</span><span class="sxs-lookup"><span data-stu-id="b471f-110">**Feature highlights:**</span></span>

<span data-ttu-id="b471f-111">Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:</span><span class="sxs-lookup"><span data-stu-id="b471f-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="b471f-112">Autenticación de Office 365 para que los agentes se conecten a su inquilino de Microsoft desde su cliente CCaaS integrado</span><span class="sxs-lookup"><span data-stu-id="b471f-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="b471f-113">Ver cuándo los agentes están disponibles con Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="b471f-114">Soporte técnico de transferencias y llamadas grupales con Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="b471f-115">API de Teams Graph y API de comunicación en la nube para la integración con Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="b471f-116">Conexión troncal SIP multiinquilino para dar soporte a varios clientes en el SBC del proveedor de soluciones.</span><span class="sxs-lookup"><span data-stu-id="b471f-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="b471f-117">Proveedores de soluciones para usar [ <span class="underline">el controlador de borde de sesión certificado por Microsoft (SBC)</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="b471f-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="b471f-118">**El modelo Extender**</span><span class="sxs-lookup"><span data-stu-id="b471f-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="b471f-119">El modelo Extender se integra con el cliente de Teams con la plataforma de cliente de [Teams,](/microsoftteams/platform/overview)las [API de Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) y la API de comunicaciones en la nube en Microsoft [Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="b471f-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="b471f-120">El modelo Extender también usa el sistema telefónico de Teams para todas las llamadas del centro de contacto y las experiencias de control de llamadas, y el proveedor de soluciones del centro de contacto actúa como operador de telefonía junto con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b471f-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="b471f-121">Los agentes pueden usar Teams para la colaboración interna y la comunicación externa y pueden beneficiarse de notas contextuales dinámicas que correlacionan datos de varios sistemas antes de iniciar una participación y, después, evitar el costoso cambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="b471f-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="b471f-122">Las organizaciones pueden diseñar flujos de trabajo y configuraciones de enrutamiento avanzadas hasta el individuo y medir la calidad de su sistema e interacciones.</span><span class="sxs-lookup"><span data-stu-id="b471f-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="b471f-123">**Características destacadas:**</span><span class="sxs-lookup"><span data-stu-id="b471f-123">**Feature highlights:**</span></span>

<span data-ttu-id="b471f-124">Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:</span><span class="sxs-lookup"><span data-stu-id="b471f-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="b471f-125">API de Teams Graph y API de comunicación en la nube para la integración con Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="b471f-126">Aplicación basada en Teams para experiencias de agente</span><span class="sxs-lookup"><span data-stu-id="b471f-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="b471f-127">Teams como el punto de conexión de llamada principal para los agentes</span><span class="sxs-lookup"><span data-stu-id="b471f-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="b471f-128">Llamadas de cliente de Teams para todos los controles de llamada</span><span class="sxs-lookup"><span data-stu-id="b471f-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="b471f-129">Aplicación de experiencia de agente para cliente web y móvil de Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="b471f-130">Análisis, administración de flujos de trabajo, experiencias basadas en roles para agentes en la aplicación CCaaS en Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="b471f-131">Experiencias de chat y colaboración integradas con clientes de Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="b471f-132">Conservar el rendimiento y la calidad de las experiencias de cliente de Teams en todas las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b471f-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="b471f-133">**El modelo Power**</span><span class="sxs-lookup"><span data-stu-id="b471f-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="b471f-134">El modelo Power permite a los proveedores de soluciones crear aplicaciones de voz nativas basadas en Azure con la infraestructura de llamadas de Teams y la plataforma de clientes para ofrecer soluciones modernas e inteligentes para la conexión colaborativa entre clientes y agentes.</span><span class="sxs-lookup"><span data-stu-id="b471f-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="b471f-135">El objetivo del modelo Power es proporcionar una experiencia de centro de contacto de una aplicación y una pantalla.</span><span class="sxs-lookup"><span data-stu-id="b471f-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="b471f-136">**Características destacadas:**</span><span class="sxs-lookup"><span data-stu-id="b471f-136">**Feature highlights:**</span></span>

<span data-ttu-id="b471f-137">Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:</span><span class="sxs-lookup"><span data-stu-id="b471f-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="b471f-138">Experiencias de agente formales habilitadas de forma nativa para la comunicación de todos los canales a través del SDK de Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="b471f-139">Usar los servicios de colaboración de Teams para la colaboración de agentes y las interacciones con los clientes</span><span class="sxs-lookup"><span data-stu-id="b471f-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="b471f-140">Aprovisionamiento rápido de servicios en la nube, implementación en cualquier lugar</span><span class="sxs-lookup"><span data-stu-id="b471f-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="b471f-141">Control de conversación directo e interacción con los usuarios durante las conversaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="b471f-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="b471f-142">El modelo Power estará disponible a finales de 2021.</span><span class="sxs-lookup"><span data-stu-id="b471f-142">The Power model will be available towards the end of 2021.</span></span>
