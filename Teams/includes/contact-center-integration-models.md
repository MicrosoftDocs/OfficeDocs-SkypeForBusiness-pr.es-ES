## <a name="integration-models-for-solution-providers"></a>Modelos de integración para proveedores de soluciones

<a name="steps"></a>

Como proveedor de soluciones de Contact Center, hay tres modelos entre los que elegir para integrar su solución de centro de contacto conectado en Teams:

- Si desea usar SBCs certificados y enrutamiento directo para conectar una solución de centro de contacto a Teams, consulte el [modelo Conectar](?tabs=connect#steps).

- Si desea usar bots de Azure y las API de Microsoft Graph Communication para habilitar a los proveedores de soluciones para crear aplicaciones de Teams, consulte el [modelo Extender](?tabs=extend#steps).

- Si desea usar un SDK que permita a los proveedores de soluciones instalar experiencias nativas de Teams en su aplicación, consulte el [modelo de Power](?tabs=power#steps). Las soluciones de energía serán posibles cuando el SDK esté disponible. Próximamente.

### <a name="the-connect-model"></a>[**El modelo Conectar**](#tab/connect)

El modelo Conectar usa SBCs y enrutamiento directo certificados por Microsoft para conectar soluciones de centro de contacto a la infraestructura del sistema telefónico de Teams, lo que permite mejorar el enrutamiento, la configuración y la información del sistema.

Los agentes pueden configurar asistentes virtuales automatizados y colas de enrutamiento basadas en aptitudes para recopilar información y conectar a los clientes con expertos en la materia.

**Características destacadas:**

Si bien estas características no son una lista completa de funciones para este modelo de integración, las áreas principales incluyen:

- Office 365 autenticación para que los agentes se conecten a su inquilino de Microsoft desde su cliente de CCaaS integrado

- Ver cuándo los agentes están disponibles con Teams

- Transferencia y soporte técnico de llamadas grupales con Teams

- API de Teams Graph y API de comunicación en la nube para la integración con Teams

- Conexión troncal SIP multiinquilino para dar soporte a varios clientes en el SBC del proveedor de soluciones.

- Proveedores de soluciones para usar el [<span class="underline">controlador de borde de sesión certificado por Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**El modelo Extender**](#tab/extend)

El modelo Extender se integra con el cliente de Teams mediante la [plataforma cliente de Teams](/microsoftteams/platform/overview), [las API de Teams Graph](/graph/api/resources/teams-api-overview) y la [API de comunicaciones en la nube de Microsoft Graph](/graph/api/resources/communications-api-overview). El modelo Extender también usa el sistema telefónico de Teams para todas las llamadas de centro de contacto y experiencias de control de llamadas, y el proveedor de soluciones del centro de contactos actúa como operador de telefonía junto con Microsoft 365.

Los agentes pueden usar Teams para la colaboración interna y la comunicación externa, y pueden beneficiarse de notas dinámicas y contextuales que correlacionan datos de varios sistemas antes de iniciar una interacción y, a continuación, evitar costosos cambios de contexto.

Las organizaciones pueden diseñar flujos de trabajo y configuraciones avanzadas de enrutamiento hacia el individuo y medir la calidad de su sistema e interacciones.

**Características destacadas:**

Si bien estas características no son una lista completa de funciones para este modelo de integración, las áreas principales incluyen:

- API de Teams Graph y API de comunicación en la nube para la integración con Teams

- Aplicación basada en Teams para experiencias de agente

- Teams como el punto de conexión de llamada principal para los agentes

- Llamada de cliente de Teams para todos los controles de llamada

- Aplicación experiencia de agente para cliente móvil y web de Teams

- Análisis, administración de flujos de trabajo, experiencias basadas en roles para agentes en la aplicación de CCaaS en Teams

- Experiencias de chat y colaboración integradas con clientes de Teams

- Conservar el rendimiento y la calidad de las experiencias de cliente de Teams en todas las aplicaciones

> [!NOTE]
> El bot de agente no necesita una licencia del sistema telefónico. El usuario de Teams necesita una licencia del sistema telefónico y un número de teléfono.

### <a name="the-power-model"></a>[**Modelo de energía**](#tab/power)

El modelo power permite a los proveedores de soluciones crear aplicaciones de voz nativas basadas en Azure mediante la infraestructura de llamadas de Teams y la plataforma cliente para ofrecer soluciones modernas e inteligentes para la conexión colaborativa entre clientes y agentes. El objetivo del modelo power es proporcionar una experiencia de centro de contactos de una sola aplicación en una pantalla.


> [!NOTE]
> Próximamente.
