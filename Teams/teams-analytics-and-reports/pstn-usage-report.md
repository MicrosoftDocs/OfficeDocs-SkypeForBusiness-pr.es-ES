---
title: Microsoft Teams Informe de uso de RTC
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Obtenga información sobre cómo usar el Teams de uso de RTC en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de llamadas y audioconferencias en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: af904400b7a20befe650977c4baea035f998cf86
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278523"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams Informe de uso de RTC

El Teams de uso de RTC (red telefónica conmutada pública) del Centro de administración de Microsoft Teams le ofrece información general sobre la actividad de llamadas y audioconferencias en su organización. Puede ver la actividad de llamadas detallada para planes de llamadas si usa Microsoft como operador de telefonía y para enrutamiento directo si usa su propio operador de telefonía.

La **pestaña Planes de** llamadas muestra información que incluye el número de minutos que los usuarios han invertido en llamadas RTC entrantes y salientes y el costo de estas llamadas. La **pestaña Enrutamiento directo** muestra información, incluida la dirección SIP y las horas de inicio y finalización de las llamadas. Use la información de este informe para obtener información sobre el uso de RTC en su organización y ayudarle a investigar, planear y tomar decisiones empresariales.

> [!NOTE]
> Si tiene un plan de llamadas de Telstra o Softbank, no verá ningún registro de detalles de llamadas en el informe de uso de RTC. Póngase en contacto con Telstra o Softbank para sus necesidades de informes. 

## <a name="view-the-pstn-usage-report"></a>Ver el informe de uso de RTC

1. En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic **en Análisis & informes de**  >  **uso.** En la pestaña **Ver informes,** en **Informe,** seleccione **Informe de uso de RTC.**
2. En **Intervalo de** fechas , seleccione un rango predefinido de 7 o 28 días, o bien establezca un rango personalizado y, a continuación, seleccione Ejecutar **informe.**

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="calling-plans"></a>Planes de llamadas

[![Captura de pantalla del informe de uso de RTC planes de llamadas en el Centro de administración](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de pantalla del informe de uso de RTC en el Microsoft Teams de administración con llamadas numeradas")](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede ver para ver las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que establezca |
|**2**   |Cada informe tiene una fecha para cuándo se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado. <br>Mantenga el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**La marca de hora (UTC)** es la hora en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Microsoft Teams de administración.</li><li>**Nombre** de usuario es el nombre de inicio de sesión del usuario.</li><li>**Teléfono número es** el número que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes.</li><li>**El tipo** de llamada es si la llamada era una llamada entrante o saliente RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamadas que puede ver incluyen:<br><br>**Teams de llamadas de usuario**<ul><li>**user_in:** el usuario recibió una llamada RTC entrante.</li><li>**user_out:** el usuario ha realizado una llamada RTC saliente</li><li>**user_out_conf:** el usuario agregó dos o más participantes RTC a la llamada, como una llamada de conferencia de tres vías</li><li>**user_out_transfer:** el usuario ha transferido la llamada a un número RTC</li><li>**user_out_forwarding:** el usuario reenvía la llamada a un número RTC</li><li>**conf_in:** una llamada entrante al puente de audioconferencia</li><li>**conf_out:** una llamada saliente desde el puente de audioconferencia normalmente para agregar un número RTC a la conferencia</li></ul><br>**Teams de llamadas de bots**<ul><li>**ucap_in:** una llamada RTC entrante a un bot Teams como el operador automático o la cola de llamadas</li><li>**ucap_out:** una llamada RTC saliente desde un bot de Teams, como el operador automático o la cola de llamadas</li></ul><br><li>**Se llama** a es el número marcado.</li><li>**Para país o región es** el país o región marcado.</li><li>**Llamado desde** es el número que ha realizado la llamada.</li><li>**De país o región** es el país o región desde donde se ha realizado la llamada.</li><li>**El** cargo es la cantidad de dinero o costo de la llamada que se carga en tu cuenta. </li><li>**Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. </li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Nacionales e** Internacionales le indica si la llamada fue nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario.</li><li>**Id. de** llamada es el id. de llamada de una llamada. Es un identificador de la llamada que puede usar al llamar al soporte técnico de Microsoft.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**País o región es** la ubicación de uso. </li> <li>**Id. de** conferencia es el id. de conferencia de la audioconferencia. </li><li>**La funcionalidad** es la licencia que se usa para la llamada. Los tipos de licencia que puede ver incluyen:<ul><li>**MCOEV o MCOEV_VIRTUALUSER o MCOEV_VIRTUALUSER_GOV:** aplicaciones de voz como Operador automático o Colas de llamadas</li><li>**FREECALL:** en caso de un problema técnico que nos impida fijar precios en una llamada, la llamada se proporciona de forma gratuita y aparecerá con esta capacidad</li><li>**MCOPSTN1** - Plan de llamadas nacionales (3000 min ee. UU. / 1200 min planes de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 minutos)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOPSTN8:** Plan de llamadas nacionales 120 min por usuario (no se agrupa entre usuarios como lo están los otros planes de llamadas)</li><li>**MCOPSTN9** - Plan de llamadas internacionales</li><li>**MCOPSTNCAP:** área común Teléfono</li><li>**MCOPSTNPP:** créditos de comunicaciones</li><li>**MCOMEETADD-** Audioconferencia</li><li>**MCOMEETADD_DIALOUT_US:** plan de acceso telefónico de Audioconferencia de EE. UU. y Canadá</li><li>**MCOMEETADD_CN_GLOBAL:** audioconferencia para usuarios que no son de China</li><li>**MCOMEETADD_TATA-** Conexiones de comunicaciones de Tata</li><li>**MCOMEETACPEA** - Audioconferencias de pago por minuto </li><li>**MCOMEETACPEA_GOV:** pago por minuto de audioconferencia para el gobierno</li></ul></li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Filtro para** filtrar el informe por nombre de usuario o tipo de llamada |
|**7**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**8**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  |

### <a name="direct-routing"></a>Enrutamiento directo

[![Captura de pantalla del informe de uso de RTC de](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de pantalla del informe de uso de RTC de enrutamiento directo en el Microsoft Teams de administración con llamadas numeradas") enrutamiento directo en el Centro de administración](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede ver para ver las tendencias de los últimos 7 o 28 días. |
|**2**   |Cada informe tiene una fecha para cuándo se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**La marca de hora (UTC)** es la hora en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Microsoft Teams de administración. El nombre también puede ser el nombre de un bot, por ejemplo, la cola de llamadas o la nube Operador automático. </li><li>**La dirección SIP** es la dirección SIP del usuario o un bot que recibió o realizó la llamada.</li><li>**El número de** llamada es el número del usuario o el bot que realizó la llamada. </li><li>**El número de destinatario** es el número del usuario o del bot que recibió la llamada. En una llamada entrante a un usuario Teams será el usuario Teams, en una llamada saliente de un usuario de Teams será el usuario RTC. </li><li>**El tipo** de llamada es si la llamada era una llamada entrante o saliente RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamada que puede ver incluyen:<br><br>**Teams de llamadas de usuario**<ul><li>**dr_in:** el usuario recibió una llamada RTC entrante</li><li>**dr_out:** el usuario ha realizado una llamada RTC saliente</li><li>**dr_out_user_conf:** el usuario agregó un participante RTC a la llamada</li><li>**user_out_transfer:** el usuario ha transferido la llamada a un número RTC</li><li>**dr_out_user_forwarding:** el usuario reenvía la llamada a un número RTC</li><li>**dr_out_user_transfer:** el usuario ha transferido la llamada a un número RTC</li><li>**dr_emergency_out:** el usuario realizó una llamada de emergencia</li></ul><br>**Teams de llamadas de bots**<ul><li>**dr_in_ucap:** una llamada RTC entrante a un bot de Teams, como el operador automático o la cola de llamadas</li><li>**dr_out_ucap:** una llamada RTC saliente desde un bot de Teams, como el operador automático o la cola de llamadas</li></ul><br><li>**Llamado a** es el número del usuario que ha recibido la llamada.</li><li>Hora de inicio **(UTC)** es la hora en la que el proxy SIP recibe la respuesta final (mensaje SIP "200 Aceptar") desde el SBC en una llamada saliente (Teams/Bot a un usuario RTC) o después de que el proxy SIP envíe la Invitación al siguiente salto dentro del back-end de Teams en una llamada entrante (usuario RTC a un Teams/Bot). </li><li>Hora de invitación **(UTC)** es la hora en la que la invitación inicial se envió en una llamada saliente desde un usuario de Teams o una llamada de bot al SBC, o se recibió en una llamada entrante a una llamada de Teams o bot por el componente proxy SIP de Enrutamiento directo desde el SBC.</li><li>**Hora de error (UTC)** es la hora en la que se ha fallado la llamada. Solo para llamadas con errores. El código SIP final, el subcódigo final de Microsoft y la frase SIP final proporcionan los motivos por los que se ha fallado la llamada y pueden ayudarle con la solución de problemas. </li><li>**Hora de finalización (UTC)** es la hora de finalización de la llamada (solo para llamadas correctas).</li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**La omisión** de medios indica si el tronco se ha habilitado para la omisión de medios. </li> <li>**FQDN de SBC** es el nombre de dominio completo (FQDN) del controlador de borde de sesión (SBC). </li><li>**La región de Azure para medios** es el centro de datos que se usó como ruta de acceso multimedia en una llamada sin omitir. </li><li>**La región de Azure para señalización** es el centro de datos que se usó para la señalización tanto para llamadas de omisión como de no omisión. </li><li>**Tipo de evento** es el tipo de evento de la llamada. Verá Éxito para las llamadas correctas e Intento de llamadas con errores. </li><li>**Código SIP final** es el código con el que finalizó la llamada.</li><li>**El subcódigo final de Microsoft** es un código que indica acciones específicas que se han producido.</li><li>**Frase SIP final** es la descripción del código SIP y el subcódigo de Microsoft.</li><li>**Id. de** correlación es un identificador único para la llamada que puede usar al llamar al soporte técnico de Microsoft.</li><li>**El id. de** correlación compartida solo está visible en el archivo CSV descargable y no existe en el portal. El id. de correlación compartida existe en al menos dos llamadas relacionadas. Vea la descripción detallada a continuación.</li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**7**   |Seleccione **Exportar a Excel** para descargar los datos en un archivo separado por comas (CSV) para analizarlos sin conexión o para usarlos como entrada para su sistema de facturación. |

#### <a name="callercallee-fields-considerations"></a>Consideraciones de los campos Llamada/Callee

Según la dirección de la llamada, los nombres de llamada o destinatario pueden contener números que no son E164.

Estos campos pueden venir de los SBC del cliente. Hay tres formatos que el SBC puede enviar a Enrutamiento directo: números E.164, números que no sean de E.164 y cadenas.

- E.164 número de teléfono de un usuario que tiene un número E.164 a un usuario que también tiene un número E.164. 
- Llamar desde un número que no es E.164. Un usuario de un PBX de terceros interconectado con Enrutamiento directo realiza una llamada a un Teams usuario. En este caso, el número de autor de la llamada puede ser cualquier número que no sea E.164, por ejemplo +1001. 
- Un spammer llama y no presenta un número, solo un nombre, por ejemplo, "Servicio de ingresos internos". Esta cadena se mostrará en los informes.

#### <a name="about-shared-correlation-id"></a>Acerca del id. de correlación compartida

El Id. de correlación compartida solo existe en el archivo Excel que descargue e indica que hay dos o más llamadas relacionadas. A continuación se explican los distintos escenarios y cuándo está presente el id. de correlación compartida.

1.    Usuario RTC 1 en un punto de conexión RTC llamado Usuario Teams 1 de Teams en un cliente, tipo de llamada Dr_In, id. de correlación 57f28917-42k5-4c0c-9433-79734873f2ac, sin identificador de correlación compartido.
2.    Teams Usuario Teams 1 en un cliente llamado Usuario RTC 1 en un punto de conexión RTC, tipo de llamada Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sin id. de correlación compartida.
3.    Usuario RTC 1 en un punto de conexión RTC denominado Teams usuario 2 en Teams cliente, tipo de llamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, id. de correlación compartida f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Llamada existente 3 con id. de correlación "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuario RTC 1 en una llamada con Teams usuario 2. Teams Usuario 2 ha transferido (ciega o consultiva) una llamada a Teams o a un usuario RTC, tipo de llamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, id. de correlación compartida f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportar los informes
Haga **clic en Exportar Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.   El proceso de exportación puede tardar entre unos segundos y varios minutos en completarse, dependiendo de la cantidad de datos.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Los archivos exportados contienen campos adicionales que no están disponibles en el informe en línea. Se pueden usar para solucionar problemas y flujos de trabajo automatizados.

 Recibirá un archivo zip denominado **"Llamadas.Export. `[identifier]`.zip**", siendo el identificador un identificador único para la exportación que se puede usar para la solución de problemas.

Si tiene planes de llamadas y enrutamiento directo, el archivo exportado puede contener datos para ambos productos. El archivo de informe de uso rtc tendrá el nombre de archivo "**RTC.calls. `[UTC date]`.csv**" y Enrutamiento directo "**DirectRouting.calls. `[UTC date]`.csv".**

 Además de los archivos RTC y Enrutamiento directo, el archivo contiene el archivo "**parameters.js** en ", con el intervalo de tiempo y las capacidades de exportación seleccionados.

Los archivos exportados están en formato de valores separados por comas (CSV), compatibles con [el estándar RFC 4180.](https://tools.ietf.org/html/rfc4180) Los archivos se pueden abrir en Excel o en cualquier otro editor que cumpla los estándares sin necesidad de realizar transformaciones.

La primera fila del ARCHIVO CSV contiene nombres de columna. Todas las fechas son UTC y en [formato ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Informe de uso de RTC exportado

 Puede exportar datos hasta un año a partir de la fecha actual, a menos que las normativas específicas del país prohíban la retención de los datos durante 12 meses.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador de llamada único |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | Id. de la audioconferencia |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Identificador del usuario que llama en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente, esto es lo mismo que la dirección SIP del usuario y puede ser igual que la dirección de correo electrónico del usuario |
> | 6 | Nombre para mostrar de usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de llamada | `nvarchar(32)` | Si la llamada era una llamada entrante o saliente RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | 10 | Nacional/Internacional | `nvarchar(16)` | Si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | 11 | Destino marcado | `nvarchar(64)` | País o región marcado |
> | 12 | Número de destino | `nvarchar(32)` | Número marcado en [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de llamada |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada |
> | 15 | Duración segundos | `int` | Cuánto tiempo estuvo conectada la llamada |
> | 16 | Tarifa de conexión | `numeric(16, 2)` | Precio de la tarifa de conexión |
> | 17 | Cargo | `numeric(16, 2)` | Cantidad de dinero o costo de la llamada que se carga en tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda usada para calcular el costo de la llamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funcionalidad | `nvarchar(32)` | La licencia usada para la llamada |

### <a name="exported-direct-routing-usage-report"></a>Informe de uso de enrutamiento directo exportado

Puede exportar datos hasta cinco meses (150 días) a partir de la fecha actual, a menos que las normativas específicas del país prohíban la retención de los datos durante ese período.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificador de llamada único |
> | 1 | Dirección SIP | `nvarchar(128)` | La dirección del usuario o bot que realizó o recibió la llamada.<br/>Tenga en cuenta que esto es realmente UserPrincipalName (UPN, nombre de inicio de sesión) en Azure Active Directory, que suele ser el mismo que la dirección SIP |
> | 2 | Nombre para mostrar | `nvarchar(128)` | El nombre de un usuario o un bot de llamadas (por ejemplo, Cola de llamadas o Operador automático) tal como se establece en Centro de administración de Microsoft 365 |
> | 3 | País de usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Hora de invitación | `datetimeoffset` | Cuando la invitación inicial envía una llamada saliente desde un usuario o bot Teams la SBC, o se recibe en la llamada entrante Teams o bot por el componente proxy SIP de Enrutamiento directo desde el SBC |
> | 5 | Hora de inicio | `datetimeoffset` | Hora en la que el proxy SIP recibió la respuesta final (mensaje SIP "200 Aceptar") desde el SBC en la salida (Teams/Bot a un usuario RTC), o después de que el proxy SIP envíe la Invitación Teams al siguiente salto dentro de un back-end en una llamada entrante (Usuario RTC a un Teams/Bot).<br/>Para las llamadas con errores y sin respuesta, puede ser igual a la hora de invitación o de error |
> | 6 | Tiempo de error | `datetimeoffset` | Solo existe para las llamadas con errores (no completamente establecidas) |
> | 7 | Hora de finalización | `datetimeoffset` | Solo existe para las llamadas correctas (totalmente establecidas). Hora en la que se ha finalizado la llamada |
> | 8 | Duración (segundos) | `int` | Duración de la llamada |
> | 9 | Correcto | `nvarchar(3)` | Sí/No. Éxito o intento |
> | 10 | Número de llamada | `nvarchar(32)` | Número del usuario o bot que realizó la llamada. En la entrada a una llamada de usuario de grupo será un usuario RTC, al salir de una llamada de usuario Teams será el número de usuario Teams usuario |
> | 12 | Número de calle | `nvarchar(32)` | Número del usuario o bot que recibió la llamada. En la entrada a una llamada de usuario de grupo será el Teams usuario, al salir de una llamada de usuario de Teams será el usuario RTC |
> | 13 | Tipo de llamada | `nvarchar(32)` | Tipo y dirección de llamada |
> | 14 | Región de Azure para medios | `nvarchar(8)` | El centro de datos usado para la ruta de acceso multimedia en una llamada sin omitir |
> | 15 | Región de Azure para señalización | `nvarchar(8)` | El centro de datos usado para la señalización tanto para llamadas de omisión como de no omisión |
> | 16 | Código SIP final | `int` | El código con el que finalizó la llamada, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Subcódigo final de Microsoft | `int` | Además de los códigos SIP, Microsoft tiene subcódigos propios que indican el problema específico |
> | 18 | Frase sip final | `nvarchar(256)` | Descripción del código SIP y el subcódigo de Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nombre de dominio completo del controlador de borde de sesión |
> | 20 | Omisión de medios | `nvarchar(3)` | Sí/No. Indica si el tronco estaba habilitado para la omisión de medios o no |
> | 21 | Id. de correlación compartida | `uniqueidentifier` | Indica que dos o más llamadas están relacionadas |


## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)