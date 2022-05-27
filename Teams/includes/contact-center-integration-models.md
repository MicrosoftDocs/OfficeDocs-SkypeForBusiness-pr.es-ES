## <a name="integration-models-for-solution-providers"></a>Modelos de integración para proveedores de soluciones

<a name="steps"></a>

Como proveedor de soluciones de Contact Center, hay tres modelos entre los que elegir para integrar su solución de centro de contacto conectado en Teams:

- Si desea usar SBCs certificados y enrutamiento directo para conectar una solución de centro de contacto a Teams, consulte el [modelo de Conectar](?tabs=connect#steps).

- Si desea usar bots de Azure y las API de comunicación de Microsoft Graph para habilitar a los proveedores de soluciones para crear aplicaciones de Teams, consulte el [modelo Extender](?tabs=extend#steps).

- Si quieres usar un SDK que permita a los proveedores de soluciones instalar experiencias de Teams nativas en su aplicación, consulta el [modelo de Power](?tabs=power#steps). Las soluciones de energía serán posibles cuando el SDK esté disponible, hacia finales de 2021.

### <a name="the-connect-model"></a>[**El modelo de Conectar**](#tab/connect)

El modelo de Conectar usa sbcs certificados por Microsoft y enrutamiento directo para conectar soluciones de centros de contacto a Teams infraestructura del sistema telefónico, lo que permite mejorar el enrutamiento, la configuración y la información del sistema.

Los agentes pueden configurar asistentes virtuales automatizados y colas de enrutamiento basadas en aptitudes para recopilar información y conectar a los clientes con expertos en la materia.

**Características destacadas:**

Si bien estas características no son una lista completa de funciones para este modelo de integración, las áreas principales incluyen:

- Office 365 autenticación para que los agentes se conecten a su inquilino de Microsoft desde su cliente de CCaaS integrado

- Ver cuándo están disponibles los agentes con Teams

- Transferencia y soporte técnico de llamadas grupales con Teams

- API de Teams Graph y comunicaciones en la nube para la integración con Teams

- Conexión troncal SIP multiinquilino para dar soporte a varios clientes en el SBC del proveedor de soluciones.

- Proveedores de soluciones para usar el [<span class="underline">controlador de borde de sesión certificado por Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**El modelo Extender**](#tab/extend)

El modelo Extend se integra con el cliente de Teams mediante la plataforma del [cliente de Teams](/microsoftteams/platform/overview), [Teams Graph API](/graph/api/resources/teams-api-overview) y [API de comunicaciones en la nube de Microsoft Graph](/graph/api/resources/communications-api-overview). El modelo Extender también usa el sistema telefónico Teams para todas las llamadas y experiencias de control de llamadas del centro de contacto, y el proveedor de soluciones de centro de contacto actúa como operador de telefonía junto con Microsoft 365.

Los agentes pueden usar Teams para la colaboración interna y la comunicación externa, y pueden beneficiarse de notas dinámicas contextuales que correlacionar datos de varios sistemas antes de iniciar una interacción y, a continuación, evitar costosos cambios de contexto.

Las organizaciones pueden diseñar flujos de trabajo y configuraciones avanzadas de enrutamiento hacia el individuo y medir la calidad de su sistema e interacciones.

**Características destacadas:**

Si bien estas características no son una lista completa de funciones para este modelo de integración, las áreas principales incluyen:

- API de Teams Graph y comunicaciones en la nube para la integración con Teams

- aplicación basada en Teams para experiencias de agente

- Teams como el punto de conexión de llamada principal para los agentes

- Teams el cliente llamando a todos los controles de llamada

- Aplicación experiencia de agente para Teams cliente web y móvil

- Análisis, administración de flujos de trabajo, experiencias basadas en roles para agentes en la aplicación de CCaaS en Teams

- Experiencias de chat y colaboración integradas con clientes de Teams

- Conservar el rendimiento y la calidad de las experiencias de cliente Teams en todas las aplicaciones

### <a name="the-power-model"></a>[**Modelo de energía**](#tab/power)

El modelo power permite a los proveedores de soluciones crear aplicaciones de voz nativas basadas en Azure mediante la infraestructura de llamadas de Teams y la plataforma cliente para ofrecer soluciones modernas e inteligentes para la conexión colaborativa entre clientes y agentes. El objetivo del modelo power es proporcionar una experiencia de centro de contactos de una sola aplicación en una pantalla.

**Características destacadas:**

Si bien estas características no son una lista completa de funciones para este modelo de integración, las áreas principales incluyen:

- Experiencias de agente formal habilitadas de forma nativa para la comunicación omnicanal a través de Teams SDK

- Usar los servicios de colaboración Teams para la colaboración de agentes y las interacciones de los clientes

- Aprovisionamiento rápido de servicios en la nube, implementación en cualquier lugar

- Control directo de la conversación e interacción con los usuarios durante las conversaciones de Teams

> [!NOTE]
> El modelo Power estará disponible a finales de 2021.
