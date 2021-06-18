## <a name="integration-models-for-solution-providers"></a>Modelos de integración para proveedores de soluciones

<a name="steps"></a>

Como proveedor de soluciones de centro de contacto, hay tres modelos entre los que elegir para integrar la solución del centro de contacto conectado en Teams:

- Si desea usar SBC certificados y Enrutamiento directo para conectar una solución de centro de contacto a Teams, vea el modelo [Conectar.](?tabs=connect#steps)

- Si desea usar los bots de Azure y las API de comunicación de Microsoft Graph para permitir que los proveedores de soluciones creen aplicaciones de Teams, vea [el modelo Extender.](?tabs=extend#steps)

- Si desea usar un SDK que permite a los proveedores de soluciones instalar experiencias nativas de Teams en su aplicación, vea [el modelo de Power.](?tabs=power#steps) Las soluciones de Power serán posibles cuando el SDK esté disponible, hacia finales de 2021.

### <a name="the-connect-model"></a>[**El modelo Conectar**](#tab/connect)

El modelo Connect usa SBC certificados por Microsoft y Enrutamiento directo para conectar soluciones del centro de contactos a la infraestructura del sistema telefónico de Teams, lo que permite mejorar el enrutamiento, la configuración y la información del sistema.

Los agentes pueden configurar asistentes virtuales automatizados y colas de enrutamiento basadas en aptitudes para recopilar información y conectar a los clientes con expertos en la materia.

**Características destacadas:**

Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:

  - Autenticación de Office 365 para que los agentes se conecten a su inquilino de Microsoft desde su cliente CCaaS integrado 

  - Ver cuándo los agentes están disponibles con Teams

  - Soporte técnico de transferencias y llamadas grupales con Teams 

  - API de Teams Graph y API de comunicación en la nube para la integración con Teams 

  - Conexión troncal SIP multiinquilino para dar soporte a varios clientes en el SBC del proveedor de soluciones.  

  - Proveedores de soluciones para usar [ <span class="underline">el controlador de borde de sesión certificado por Microsoft (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**El modelo Extender**](#tab/extend)

El modelo Extender se integra con el cliente de Teams con la plataforma de cliente de [Teams,](/microsoftteams/platform/overview)las [API de Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) y la API de comunicaciones en la nube en Microsoft [Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) El modelo Extender también usa el sistema telefónico de Teams para todas las llamadas del centro de contacto y las experiencias de control de llamadas, y el proveedor de soluciones del centro de contacto actúa como operador de telefonía junto con Microsoft 365.

Los agentes pueden usar Teams para la colaboración interna y la comunicación externa y pueden beneficiarse de notas contextuales dinámicas que correlacionan datos de varios sistemas antes de iniciar una participación y, después, evitar el costoso cambio de contexto.

Las organizaciones pueden diseñar flujos de trabajo y configuraciones de enrutamiento avanzadas hasta el individuo y medir la calidad de su sistema e interacciones.

**Características destacadas:**

Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:

  - API de Teams Graph y API de comunicación en la nube para la integración con Teams 

  - Aplicación basada en Teams para experiencias de agente 

  - Teams como el punto de conexión de llamada principal para los agentes 

  - Llamadas de cliente de Teams para todos los controles de llamada

  - Aplicación de experiencia de agente para cliente web y móvil de Teams

  - Análisis, administración de flujos de trabajo, experiencias basadas en roles para agentes en la aplicación CCaaS en Teams

  - Experiencias de chat y colaboración integradas con clientes de Teams 

  - Conservar el rendimiento y la calidad de las experiencias de cliente de Teams en todas las aplicaciones  

### <a name="the-power-model"></a>[**El modelo Power**](#tab/power)

El modelo Power permite a los proveedores de soluciones crear aplicaciones de voz nativas basadas en Azure con la infraestructura de llamadas de Teams y la plataforma de clientes para ofrecer soluciones modernas e inteligentes para la conexión colaborativa entre clientes y agentes. El objetivo del modelo Power es proporcionar una experiencia de centro de contacto de una aplicación y una pantalla.

**Características destacadas:**

Aunque estas características no son una lista completa de funcionalidades de características para este modelo de integración, las áreas de enfoque incluyen:

  - Experiencias de agente formales habilitadas de forma nativa para la comunicación de todos los canales a través del SDK de Teams 

  - Usar los servicios de colaboración de Teams para la colaboración de agentes y las interacciones con los clientes  

  - Aprovisionamiento rápido de servicios en la nube, implementación en cualquier lugar 

  - Control de conversación directo e interacción con los usuarios durante las conversaciones de Teams 

>[!NOTE]
> El modelo Power estará disponible a finales de 2021.
