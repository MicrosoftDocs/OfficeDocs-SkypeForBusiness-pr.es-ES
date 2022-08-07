---
title: Informe de uso de RTC de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo usar el informe de uso de RTC de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de llamadas y audioconferencias en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 1539f679225334f71855300a54c4fba950ddd8f8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267635"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Informe de uso de RTC de Microsoft Teams

El informe de uso de La red telefónica conmutada (RTC) de Teams del Centro de administración de Microsoft Teams le ofrece información general sobre la actividad de llamadas y audioconferencias en su organización. Puede ver la actividad de llamadas detallada para planes de llamadas si usa Microsoft como operador de telefonía y enrutamiento directo si usa su propio operador de telefonía.

La pestaña **Planes de llamadas** muestra información, incluido el número de minutos que los usuarios dedicaron a llamadas RTC entrantes y salientes y el coste de estas llamadas. La pestaña **Enrutamiento directo** muestra información, incluida la dirección SIP y las horas de inicio y finalización de llamadas. Use la información de este informe para obtener información sobre el uso de RTC en su organización y ayudarle a investigar, planificar y tomar decisiones empresariales.

> [!NOTE]
> Si tiene un plan de llamadas Telstra o Softbank, no verá registros de detalles de llamadas en el informe uso de RTC. Póngase en contacto con Telstra o Softbank para informar de sus necesidades. 

## <a name="view-the-pstn-usage-report"></a>Ver el informe de uso de RTC

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Informe de uso de RTC**.
2. En **Intervalo de fechas**, seleccione un intervalo predefinido de 7 o 28 días, o establezca un intervalo personalizado y, después, seleccione **Ejecutar informe**.

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="calling-plans"></a>Planes de llamadas

   ![Captura de pantalla del informe de uso de RTC de planes de llamadas en el centro de administración](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Captura de pantalla del informe de uso de RTC en el Centro de administración de Microsoft Teams con llamadas numeradas](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe para ver las tendencias de los últimos 7, 28 días o un intervalo de fechas personalizado que haya establecido. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado. <br>Mantenga el mouse sobre el punto de una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es la hora a la que se inició la llamada.</li><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams.</li><li>**Nombre de usuario** es el nombre de inicio de sesión del usuario.</li><li>**Número de teléfono** es el número que recibió la llamada para llamadas entrantes o el número marcado para las llamadas salientes.</li><li>**El tipo de llamada** es si la llamada era una llamada RTC de salida o entrante y el tipo de llamada como, por ejemplo, una llamada realizada por un usuario o una audioconferencia. Entre los tipos de llamadas que puede ver se incluyen:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**user_in** : el usuario recibió una llamada RTC entrante</li><li>**user_out** : el usuario realizó una llamada RTC saliente</li><li>**user_out_conf** : el usuario agregó dos o más participantes de RTC a la llamada, como una llamada de conferencia de tres vías.</li><li>**user_out_transfer** : el usuario ha transferido la llamada a un número RTC</li><li>**user_out_forwarding** : el usuario desvió la llamada a un número DE RTC</li><li>**conf_in** : una llamada entrante al puente de Audioconferencia</li><li>**conf_out** : una llamada saliente desde el puente de Audioconferencia normalmente para agregar un número RTC a la conferencia</li><li>**unassigned_in** : una llamada RTC entrante a través de un plan de llamadas a un número no asignado</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**ucap_in** : una llamada RTC entrante a un bot de Teams como un operador automático o una cola de llamadas</li><li>**ucap_out** : una llamada RTC saliente desde un bot de Teams como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado a** es el número marcado.</li><li>**Para el país o la región** se marca el país o la región.</li><li>**Llamar desde** es el número que realizó la llamada.</li><li>**Desde el país o la región** se encuentra el país o región desde el que se realizó la llamada.</li><li>**El cargo** es la cantidad de dinero o el coste de la llamada que se carga en tu cuenta. </li><li>**Moneda** es el tipo de moneda que se usa para calcular el coste de la llamada. </li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Nacional o internacional** indica si la llamada fue nacional (dentro de un país o región) o internacional (fuera de un país o región) según la ubicación del usuario.</li><li>**Identificador de llamada** es el identificador de llamada de una llamada. Es un identificador de la llamada que puede usar al llamar a Soporte técnico de Microsoft.</li><li>**Tipo** de número es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**País o región** es la ubicación de uso. </li> <li>**Id** . de conferencia es el id. de conferencia de la audioconferencia. </li><li>**Funcionalidad** es la licencia que se usa para la llamada. Entre los tipos de licencia que puede ver se incluyen:<ul><li>**MCOEV o MCOEV_VIRTUALUSER o MCOEV_VIRTUALUSER_GOV** : aplicaciones de voz como el operador automático o las colas de llamadas</li><li>**FREECALL** - En caso de un problema técnico que nos impida fijar el precio de una llamada, la llamada se proporciona de forma gratuita y aparecerá con esta capacidad</li><li>**MCOPSTN1** - Plan de llamadas nacionales (planes de 3000 min EE. UU. / 1200 min de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 minutos)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOPSTN8** - Plan de llamadas nacionales 120 minutos por usuario (no agrupado entre usuarios como los demás planes de llamadas)</li><li>**MCOPSTN9** - Plan de llamadas internacionales</li><li>**MCOPSTNCAP** - Teléfono de área común</li><li>**MCOPSTNPP** - Créditos de Comunicaciones</li><li>**MCOMEETADD** : Audioconferencia</li><li>**MCOMEETADD_DIALOUT_US** : plan de llamadas entrantes de Audioconferencia en Estados Unidos y Canadá</li><li>**MCOMEETADD_CN_GLOBAL** : Audioconferencia para usuarios que no son de China</li><li>**MCOMEETADD_TATA** : conexiones de Tata Communications</li><li>**MCOMEETACPEA** : pago por minuto de audioconferencia </li><li>**MCOMEETACPEA_GOV** : pago por minuto de audioconferencia para la administración pública</li></ul></li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Filtro** para filtrar el informe por nombre de usuario o tipo de llamada. |
|**7**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**8**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Haga clic en **Exportar a Excel** y, a continuación, en la pestaña **Descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.|

### <a name="direct-routing"></a>Enrutamiento directo

   ![Captura de pantalla del informe de uso de RTC de enrutamiento directo en el centro de administración](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Captura de pantalla del informe de uso de RTC de enrutamiento directo en el Centro de administración de Microsoft Teams con llamadas numeradas](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe para ver las tendencias de los últimos 7 o 28 días. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado.<br>Mantenga el mouse sobre el punto de una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es la hora a la que se inició la llamada.</li><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. El nombre también puede ser el nombre de un bot, por ejemplo, la cola de llamadas o el operador automático de la nube. </li><li>**Dirección SIP** es la dirección SIP del usuario o un bot que recibió o realizó la llamada.</li><li>**Número de llamada** es el número del usuario o bot que realizó la llamada. </li><li>**Número de destinatario** es el número del usuario o bot que recibió la llamada. En una llamada entrante a un usuario de Teams será el usuario de Teams, en una llamada saliente de un usuario de Teams será el usuario de RTC. </li><li>**El tipo de llamada** es si la llamada era una llamada RTC de salida o entrante y el tipo de llamada como, por ejemplo, una llamada realizada por un usuario o una audioconferencia. Entre los tipos de llamadas que puede ver se incluyen:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**dr_in** : el usuario recibió una llamada RTC entrante</li><li>**dr_out** : el usuario realizó una llamada RTC saliente</li><li>**dr_out_user_conf** : el usuario agregó un participante de RTC a la llamada</li><li>**dr_out_user_forwarding** : el usuario desvió la llamada a un número DE RTC</li><li>**dr_out_user_transfer** : el usuario ha transferido la llamada a un número DE RTC</li><li>**dr_emergency_out** : el usuario realizó una llamada de emergencia</li><li>**dr_unassigned_in** : una llamada RTC entrante a través de enrutamiento directo a un número sin asignar</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**dr_in_bot** : una llamada RTC entrante a un bot de Teams como un operador automático o una cola de llamadas</li><li>**dr_out_bot** : una llamada RTC saliente de un bot de Teams como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado a** es el número del usuario que recibió la llamada.</li><li>**Hora de inicio (UTC)** es la hora en que el proxy SIP recibe la respuesta final (mensaje SIP "200 Correcto") desde el SBC en una llamada saliente (Teams/Bot a un usuario DE RTC), o después de que el proxy SIP envíe la invitación al próximo salto dentro del back-end de Teams en una llamada entrante (usuario de RTC a un equipo o bot). </li><li>**Hora de la invitación (UTC)** es la hora en que la invitación inicial se envió en una llamada saliente desde un usuario de Teams o una llamada de bot al SBC, o se recibió en una llamada entrante a una llamada de bot o de Teams por el componente proxy SIP de Enrutamiento directo desde el SBC.</li><li>**Tiempo de error (UTC)** es la hora en que se ha dado un error en la llamada. Solo para llamadas con errores. El código SIP final, el subcódigo final de Microsoft y la frase SIP final proporcionan los motivos por los que la llamada falló y pueden ayudarle con la solución de problemas. </li><li>**Hora de finalización (UTC)** es la hora a la que finalizó la llamada (solo para las llamadas correctas).</li><li>**Duración** es el tiempo durante el que se conectó la llamada, desde la invitación hasta el final de la llamada o el error. Para el desvío de llamadas, la duración incluye la llamada en la cola de llamadas.</li><li>**Tipo** de número es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**La omisión de medios** indica si el tronco se ha habilitado para la omisión de medios. </li> <li>**SBC FQDN** es el nombre de dominio completo (FQDN) del controlador de borde de sesión (SBC). </li><li>**Azure region for Media** es el centro de datos que se usó como ruta de acceso multimedia en una llamada que no se omite. </li><li>**Azure region for Signaling** es el centro de datos que se usó para la señalización para llamadas de derivación y sin bypass. </li><li>**Tipo de evento** es el tipo de evento de la llamada. Verá Éxito de las llamadas correctas e Intento de llamadas con errores. </li><li>**Código SIP final** es el código con el que finalizó la llamada.</li><li>**El subcódigo final de Microsoft** es un código que indica acciones específicas que se han producido.</li><li>**Frase SIP final** es la descripción del código SIP y el subcódigo de Microsoft.</li><li>Id. de **correlación** es un identificador único de la llamada que puede usar al llamar a Soporte técnico de Microsoft.</li><li>**El Id. de correlación compartida** solo está visible en el archivo CSV descargable y no existe en el portal. El id. de correlación compartido existe en al menos dos llamadas relacionadas. Consulta la descripción detallada a continuación.</li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**7**   |Seleccione **Exportar a Excel** para descargar los datos en un archivo separado por comas (CSV) para realizar análisis sin conexión o para usarlos como entrada para su sistema de facturación. |

#### <a name="callercallee-fields-considerations"></a>Consideraciones de los campos Llamador/Destinatario de llamadas

Según la dirección de la llamada, los nombres del autor de la llamada o destinatario de la llamada pueden contener números que no sean E164.

Estos campos pueden proceder de los SBC del cliente. Hay tres formatos que el SBC puede enviar a enrutamiento directo: números E.164, números que no son E.164 y cadenas.

- Número de teléfono E.164 de un usuario que tiene un número E.164 a un usuario que también tiene un número E.164. 
- Llamar desde un número que no es E.164. Un usuario de PBX de terceros interconectado con enrutamiento directo realiza una llamada a un usuario de Teams. En este caso, el número del autor de la llamada podría ser cualquier número que no sea E.164, por ejemplo +1001. 
- Un spammer llama y no presenta un número, solo un nombre, por ejemplo "Servicio de ingresos internos". Esta cadena se mostrará en los informes.

#### <a name="phone-number-obfuscation"></a>Ofuscación del número de teléfono
Los requisitos de privacidad por país incluyen la ofuscación de los números de teléfono externos (no propiedad del cliente). Los tres o cuatro últimos dígitos del número de teléfono se reemplazan por asteriscos (+123 456789***). 

Para las llamadas entrantes, se ofusca el número de la persona que llama, en el caso de las llamadas salientes, el número del destinatario de la llamada se ofusca. Esto se aplica a los informes de enrutamiento directo y RTC del Centro de Administración inquilinos, a la exportación de datos y a los registros de llamadas disponibles a través de Microsoft Graph.

La ofuscación se basa en la ubicación de la organización (país). Los números de teléfono completos se muestran para los países que no aparecen en la tabla siguiente:

| País | Número de dígitos de ofuscación |
| :-: | :- |
|BE: Bélgica | 3 |
|CH: Suiza | 4 |
|DE: Alemania | 3 |
|DK: Dinamarca | 3 |
|ES: España | 3 |
|FI: Finlandia | 3 |
|FR: Francia | 4 |
|TI: Italia | 3 |
|NL - Países Bajos | 3 |
|NO - Noruega | 3 |
|SE - Suecia | 3 |

#### <a name="about-shared-correlation-id"></a>Acerca del id. de correlación compartida

El Id. de correlación compartida solo existe en el archivo de Excel exportado que se descarga e indica que hay dos o más llamadas relacionadas. A continuación se explican los diferentes escenarios y cuándo está presente el Id. de correlación compartida.

1.    Usuario de RTC 1 en un punto de conexión DE RTC llamado Usuario de Teams 1 en el cliente de Teams, tipo de llamada Dr_In, id. de correlación 57f28917-42k5-4c0c-9433-79734873f2ac, sin id. de correlación compartido.
2.    Usuario 1 de Teams en el cliente de Teams llamado Usuario de RTC 1 en un punto de conexión RTC, tipo de llamada Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sin id. de correlación compartido.
3.    Usuario de RTC 1 en un punto de conexión DE RTC denominado Usuario de Teams 2 en el cliente de Teams, tipo de llamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, id. de correlación compartido f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Llamada 3 existente con id. de correlación "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuario de RTC 1 en una llamada con el usuario 2 de Teams. El usuario de Teams 2 ha transferido (ciego o consultativo) una llamada a Teams o usuario RTC, el tipo de llamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, el id. de correlación compartido f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportar los informes
Haga clic en **Exportar a Excel** y, a continuación, en la pestaña **Descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo. El proceso de exportación puede tardar de unos segundos a varios minutos en completarse, dependiendo de la cantidad de datos.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Los archivos exportados contienen campos adicionales que no están disponibles en el informe en línea. Estos se pueden usar para solucionar problemas y flujos de trabajo automatizados.

 Recibirá un archivo zip denominado "**Calls.Export.`[identifier]`.zip**", siendo el identificador un identificador único para la exportación que se puede usar para solucionar problemas.

Si tiene planes de llamadas y enrutamiento directo, el archivo exportado puede contener datos para ambos productos. El archivo de informe de uso de RTC tendrá el nombre de archivo "**RTC.llamadas.`[UTC date]`.csv**" y Enrutamiento directo "**DirectRouting.calls.`[UTC date]`.csv**".

 Además de los archivos de enrutamiento directo y RTC, el archivo contiene el archivo "**parameters.json**", con el intervalo de tiempo de exportación seleccionado y las capacidades.

Los archivos exportados están en formato de valores separados por comas (CSV), conforme al estándar [RFC 4180](https://tools.ietf.org/html/rfc4180) . Los archivos se pueden abrir en Excel o en cualquier otro editor compatible con estándares sin necesidad de transformaciones.

La primera fila del CSV contiene los nombres de columna. Todas las fechas son UTC y tienen formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Informe de uso de RTC exportado

 Puede exportar datos hasta un año desde la fecha actual, a menos que las normativas específicas del país prohíban la retención de los datos durante 12 meses.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador de llamada único |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | Id. de la audioconferencia |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Llamar al identificador de usuario en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamadas de bot (ucap_in, ucap_out) |
> | 5 | Upn | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente es la misma que la dirección SIP del usuario y puede ser la misma que la dirección de correo electrónico del usuario. |
> | 6 | Nombre para mostrar de usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que ha recibido la llamada de llamadas entrantes o el número marcado para las llamadas salientes. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de llamada | `nvarchar(32)` | Si la llamada era una llamada RTC de salida o entrante y el tipo de llamada como, por ejemplo, una llamada realizada por un usuario o una audioconferencia |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | 10 | Nacional e internacional | `nvarchar(16)` | Si la llamada fue nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | 11 | Destino marcado | `nvarchar(64)` | País o región marcado |
> | 12 | Número de destino | `nvarchar(32)` | Número marcado en formato [E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de la llamada |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada |
> | 15 | Duración segundos | `int` | Cuánto tiempo se conectó la llamada |
> | 16 | Tarifa de conexión | `numeric(16, 2)` | Precio de la tarifa de conexión |
> | 17 | Cargo | `numeric(16, 2)` | Cantidad de dinero o coste de la llamada que se ha cargado a tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda usada para calcular el costo de la llamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funcionalidad | `nvarchar(32)` | La licencia usada para la llamada |

### <a name="exported-direct-routing-usage-report"></a>Informe de uso de enrutamiento directo exportado

Puede exportar datos hasta cinco meses (150 días) desde la fecha actual, a menos que las normativas específicas del país prohíban la conservación de los datos durante ese período.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificador de llamada. Varias piernas de la misma llamada pueden compartir el mismo CorrelationId |
> | 1 | AAD ObjectId | `uniqueidentifier` | Llamar al identificador de usuario en Azure Active Directory.<br/> Esta y otra información de usuario pueden ser nulas o vacías para los tipos de llamadas de bot |
> | 2 | Upn | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión, Azure Active Directory) del usuario o bot que realizó o recibió la llamada.<br/>Normalmente es la misma que la dirección SIP del usuario y puede ser la misma que la dirección de correo electrónico del usuario. |
> | 3 | Nombre para mostrar | `nvarchar(128)` | El nombre de un usuario o un bot de llamadas (por ejemplo, cola de llamadas o operador automático) tal y como se establece en Centro de administración de Microsoft 365 |
> | 4 | País de usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | Hora de invitación | `datetimeoffset` | Cuando la invitación inicial se envía de salida desde un usuario de Teams o una llamada bot a la SBC, o se recibe en una llamada entrante a Teams o llamada de bot por el componente de proxy SIP de Enrutamiento directo desde el SBC |
> | 6 | Hora de inicio | `datetimeoffset` | Hora en que el proxy SIP recibió la respuesta final (mensaje SIP "200 Aceptar") desde el SBC en saliente (Teams/Bot a un usuario RTC), o después de que el proxy SIP envíe la invitación al próximo salto dentro del back-end de Teams en una llamada entrante (usuario de RTC a un equipo/bot).<br/>Para las llamadas con errores y sin responder, esto puede ser igual a tiempo de invitación o de error |
> | 7 | Tiempo de error | `datetimeoffset` | Solo existe para las llamadas con errores (no totalmente establecidas) |
> | 8 | Hora de finalización | `datetimeoffset` | Solo existe para las llamadas correctas (completamente establecidas). Hora en la que finalizó la llamada |
> | 9 | Duración (segundos) | `int` | Duración de la llamada, desde la invitación hasta el final o el error de la llamada. Para el desvío de llamadas, la duración incluye la llamada en la cola de llamadas. |
> | 10 | Correcto | `nvarchar(3)` | Sí/No. Éxito o intento |
> | 11 | Número de autor de la llamada | `nvarchar(32)` | Número del usuario o bot que realizó la llamada. En la entrada a una llamada de un usuario de equipo será un usuario de RTC, al salir de la llamada de usuario de Teams será el número de usuario de Teams |
> | 12 | Número de destinatario | `nvarchar(32)` | Número del usuario o bot que recibió la llamada. En la entrada a una llamada de usuario de equipo será el usuario de Teams, en la llamada saliente desde el usuario de Teams será el usuario de RTC |
> | 13 | Tipo de llamada | `nvarchar(32)` | Tipo de llamada y dirección |
> | 14 | Región de Azure para medios | `nvarchar(8)` | Centro de datos usado para la ruta de acceso multimedia en llamadas que no son de omisión |
> | 15 | Región de Azure para la señalización | `nvarchar(8)` | El centro de datos usado para la señalización para llamadas de omisión y sin omisión |
> | 16 | Código SIP final | `int` | El código con el que finalizó la llamada, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Subcódigo final de Microsoft | `int` | Además de los códigos SIP, Microsoft tiene sus propios subcódigos que indican el problema específico |
> | 18 | Frase SIP final | `nvarchar(256)` | Descripción del código SIP y el subcódigo de Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nombre de dominio completo del controlador de borde de sesión |
> | 20 | Omisión de medios | `nvarchar(3)` | Sí/No. Indica si el tronco se ha habilitado para la omisión de medios o no |
> | 21 | Id. de correlación compartida | `uniqueidentifier` | Indica que dos o más llamadas están relacionadas |


## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [Informe de llamadas RTC en Microsoft Graph](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Informe de enrutamiento directo en Microsoft Graph](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
