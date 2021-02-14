---
title: Informe de uso de RTC de Microsoft Teams
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
description: Obtenga información sobre cómo usar el informe de uso de RTC de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de llamadas y audioconferencias en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc2b1ae0b6df29e29a55152dbafb9b76ae31e973
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809300"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Informe de uso de RTC de Microsoft Teams

El informe uso de RTC de Teams en el Centro de administración de Microsoft Teams le ofrece una descripción general de la actividad de llamadas y audioconferencias de su organización. Puede ver actividad de llamadas detallada para planes de llamadas si usa Microsoft como su operador de telefonía y para enrutamiento directo si usa su propio operador de telefonía.

La **pestaña Planes de** llamadas muestra información, como el número de minutos dedicados por los usuarios a llamadas RTC entrantes y salientes, así como el coste de dichas llamadas. La **pestaña Enrutamiento directo** muestra información, incluida la dirección SIP y las horas de inicio y finalización de la llamada. Use la información de este informe para obtener información sobre el uso de RTC en su organización y ayudarle a investigar, planificar y tomar decisiones empresariales.

> [!NOTE]
> Si tiene un plan de llamadas de Telstra o Softbank, no verá registros de detalles de las llamadas en el informe de uso de RTC. Ponte en contacto con Telstra o Softbank para ver tus necesidades de informes. 

## <a name="view-the-pstn-usage-report"></a>Ver el informe uso de RTC

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione **Informe de uso de RTC.**
2. En **Intervalo de** fechas, seleccione un intervalo predefinido de 7 o 28 días, o establezca un intervalo personalizado y, a continuación, seleccione Ejecutar **informe.**

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="calling-plans"></a>Planes de llamadas

[![Captura de pantalla del informe de uso de RTC de planes de llamadas en el centro de administración](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de pantalla del informe de uso de RTC en el Centro de administración de Microsoft Teams con llamadas numeradas")](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe para ver las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que establezca |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas en el período de tiempo seleccionado. <br>Mueva el puntero sobre el punto de una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**La marca de tiempo (UTC)** es la hora a la que se inicia la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams.</li><li>**Nombre de** usuario es el nombre de inicio de sesión del usuario.</li><li>**El número de** teléfono es el número que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes.</li><li>**El tipo** de llamada indica si la llamada era una llamada entrante o saliente con RTC y el tipo de llamada, como una llamada realizada por un usuario o una audioconferencia. Entre los tipos de llamadas que verá se incluyen:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**user_in:** el usuario ha recibido una llamada RTC entrante.</li><li>**user_out:** el usuario ha realizado una llamada RTC saliente</li><li>**user_out_conf:** el usuario ha agregado dos o más participantes de RTC a la llamada, como una llamada de conferencia de tres vías.</li><li>**user_out_transfer:** el usuario ha transferido la llamada a un número DE RTC</li><li>**user_out_forwarding:** el usuario desvía la llamada a un número DE RTC</li><li>**conf_in-** una llamada entrante al puente de Audioconferencia</li><li>**conf_out:** una llamada saliente desde el puente de Audioconferencia normalmente para agregar un número de RTC a la conferencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**ucap_in:** una llamada RTC entrante al bot de Teams, como un operador automático o una cola de llamadas</li><li>**ucap_out:** una llamada RTC saliente desde un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Se llama** al número marcado.</li><li>**Para el país o la región** es el país o la región que se ha marcado.</li><li>**Llamar desde** es el número desde el que se ha realizado la llamada.</li><li>**Del país o la región** es el país o la región desde donde se ha realizado la llamada.</li><li>**El** cargo es la cantidad de dinero o coste de la llamada que se cargará en tu cuenta. </li><li>**Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. </li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Domestic/International** tells you whether the call was domestic (within a country or region) or international (outside a country or region) based on the user's location.</li><li>**El identificador de** llamada es el identificador de llamada de una llamada. Es un identificador de la llamada que puede usar al llamar al Soporte técnico de Microsoft.</li><li>**El tipo de** número es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**País o región es** la ubicación de uso. </li> <li>**Id. de conferencia** es el id. de conferencia de la audioconferencia. </li><li>**La funcionalidad** es la licencia usada para la llamada. Los tipos de licencia que puede ver incluyen:<ul><li>**MCOPSTNPP-** Créditos de comunicaciones</li><li>**MCOEV o MCOEV_VIRTUALUSER:** aplicaciones de voz como operador automático o colas de llamadas</li><li>**FREECALL:** en caso de problema técnico que nos impida precios de una llamada, la llamada se proporciona de forma gratuita y aparecerá con esta capacidad</li><li>**MCOPSTN1** - Plan de llamadas nacionales (3000 min para EE. UU. /1200 min en planes de la UE)</li><li>**MCOPSTN2** - Plan de llamadas internacionales</li><li>**MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 min)</li><li>**MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 minutos)</li><li>**MCOMEETADD** - Audioconferencia</li><li>**MCOMEETACPEA** - Audioconferencia de pago por minuto</li></ul></li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Filtro para** filtrar el informe por nombre de usuario o tipo de llamada |
|**7**   |Seleccione **Pantalla completa** para ver el informe en el modo de pantalla completa. |
|**8**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  |

### <a name="direct-routing"></a>Enrutamiento directo

[![Captura de pantalla del informe de uso de](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de pantalla del informe de uso de RTC de enrutamiento directo en el Centro de administración de Microsoft Teams con llamadas numeradas") RTC de enrutamiento directo en el centro de administración](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe para ver las tendencias de los últimos 7 o 28 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas en el período de tiempo seleccionado.<br>Mueva el puntero sobre el punto de una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla proporciona un desglose del uso de RTC por llamada. <ul><li>**La marca de tiempo (UTC)** es la hora a la que se inició la llamada.</li><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. El nombre también puede ser el nombre de un bot, por ejemplo, la cola de llamadas o la nube Operador automático. </li><li>**La dirección SIP** es la dirección SIP del usuario o un bot que recibió o realizó la llamada.</li><li>**El número de** autor de la llamada es el número del usuario o del bot que hizo la llamada. </li><li>**El número del destinatario** es el número del usuario o del bot que ha recibido la llamada. En una llamada entrante a un usuario de Teams será el usuario de Teams, en una llamada saliente de un usuario de Teams será el usuario de RTC. </li><li>**El tipo** de llamada indica si la llamada era una llamada entrante o saliente con RTC y el tipo de llamada, como una llamada realizada por un usuario o una audioconferencia. Los tipos de llamada que puede ver incluyen:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**dr_in:** el usuario recibió una llamada RTC entrante</li><li>**dr_out:** el usuario ha realizado una llamada RTC saliente</li><li>**dr_out_user_conf:** el usuario agregó un participante de RTC a la llamada.</li><li>**user_out_transfer:** el usuario ha transferido la llamada a un número de RTC</li><li>**dr_out_user_forwarding:** el usuario desvía la llamada a un número DE RTC</li><li>**dr_out_user_transfer:** el usuario ha transferido la llamada a un número DE RTC</li><li>**dr_emergency_out:** el usuario realizó una llamada de emergencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**dr_in_ucap:** una llamada RTC entrante a un bot de Teams, como un operador automático o una cola de llamadas</li><li>**dr_out_ucap:** una llamada RTC saliente de un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Se llama** al número de usuario que ha recibido la llamada.</li><li>La hora de inicio **(UTC)** es la hora en la que el proxy SIP recibe la respuesta final (mensaje SIP "200 Aceptar") del SBC en una llamada saliente (Equipos/Bot a un usuario RTC), o después de que el proxy SIP envíe la invitación al próximo salto back-end de Teams en una llamada entrante (el usuario de RTC a un equipo/bot). </li><li>La hora de la invitación **(UTC)** es la hora en la que se envió la invitación inicial en una llamada saliente de un usuario o bot de Teams a la SBC, o cuando se recibió en una llamada entrante a una llamada de Teams o bot por el componente proxy SIP de enrutamiento directo desde el SBC.</li><li>**La hora de error (UTC)** es la hora en que se ha produce un error en la llamada. Solo para llamadas con errores. El código SIP final, el subcodificado final de Microsoft y la frase SIP final proporcionan los motivos por los que se ha generado un error en la llamada y pueden ayudar a la solución de problemas. </li><li>**La hora de finalización (UTC)** es la hora a la que ha finalizado la llamada (solo para llamadas correctas).</li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**El tipo de** número es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**La omisión de** medios indica si el tronco se habilitó para la omisión de medios. </li> <li>**FQDN de SBC** es el nombre de dominio completo (FQDN) del controlador de borde de sesión (SBC). </li><li>**La región de Azure para medios** es el centro de datos que se usó como ruta multimedia en una llamada que no se omita. </li><li>**Azure Region for Signaling** is the data center that was used for signaling for both bypass and non-bypass calls. </li><li>**El tipo de** evento es el tipo de evento de la llamada. Verá llamadas correctas e intentos de llamadas con errores. </li><li>**El código SIP final** es el código con el que finaliza la llamada.</li><li>**El subcodigo final** de Microsoft es un código que indica acciones específicas realizadas.</li><li>**La frase SIP** final es la descripción del código SIP y el subcode de Microsoft.</li><li>**El Id. de** correlación es un identificador único para la llamada que puede usar al llamar al Soporte técnico de Microsoft.</li><li>**El Id. de correlación** compartida solo está visible en el archivo CSV descargable y no existe en el portal. El Id. de correlación compartida existe en al menos dos llamadas que están relacionadas. Consulta la descripción detallada a continuación.</li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **Pantalla completa** para ver el informe en el modo de pantalla completa. |
|**7**   |Seleccione Exportar a **Excel** para descargar los datos en un archivo separado por comas (CSV) para analizarlos sin conexión o para usarlos como entrada en su sistema de facturación. |

#### <a name="callercallee-fields-considerations"></a>Consideraciones de los campos Autor y destinatario de la llamada

Según la dirección de la llamada, los nombres del autor de la llamada o del destinatario de la llamada pueden contener números que no son E164.

Estos campos pueden proceden del SBC del cliente. Hay tres formatos que puede enviar el SBC a Enrutamiento directo: números E.164, números que no sean E.164 y cadenas.

- Número de teléfono E.164 de un usuario con un número E.164 a un usuario que también tiene un número E.164. 
- Llamar desde un número que no es E.164. Un usuario de un PBX de terceros interconectado con enrutamiento directo realiza una llamada a un usuario de Teams. En este caso, el número del autor de la llamada puede ser cualquier número que no sea E.164, por ejemplo + 1001. 
- Un spammer llama y no presenta un número, solo un nombre, por ejemplo, "Servicio de ingresos internos". Esta cadena se mostrará en los informes.

#### <a name="about-shared-correlation-id"></a>Acerca del Id. de correlación compartida

El Id. de correlación compartida solo existe en el archivo de Excel exportado que se descarga e indica que dos o más llamadas están relacionadas. A continuación se explican los distintos escenarios y cuándo está presente el Id. de correlación compartida.

1.    Usuario de RTC 1 en un punto de conexión de RTC llamado Usuario 1 de Teams en el cliente de Teams, tipo de llamada Dr_In, id. de correlación 57f28917-42k5-4c0c-9433-79734873f2ac, ningún id. de correlación compartida.
2.    Usuario 1 de Teams en el cliente de Teams llamado Usuario RTC 1 en un punto de conexión de RTC, tipo de llamada Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sin id. de correlación compartida.
3.    Usuario de RTC 1 en un punto de conexión de RTC llamado Usuario de Teams 2 en el cliente de Teams, tipo de llamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, id. de correlación compartida f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Llamada 3 existente con id. de correlación "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuario RTC 1 en una llamada con el Usuario de Teams 2. El Usuario de Teams 2 ha transferido (ciega o consultada) una llamada a Teams o usuario RTC, al tipo de llamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, id. de correlación compartida f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportar los informes
Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.   El proceso de exportación puede tardar entre unos pocos segundos y varios minutos en completarse, dependiendo de la cantidad de datos.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Los archivos exportados contienen campos adicionales que no están disponibles en el informe en línea. Pueden usarse para solucionar problemas y flujos de trabajo automatizados.

 Recibirá un archivo zip denominado **"Llamadas.Export. `[identifier]` zip**", con el identificador como un identificador único de la exportación que se puede usar para solucionar problemas.

Si tiene planes de llamadas y enrutamiento directo, el archivo exportado puede contener datos de ambos productos. El archivo de informe de uso de RTC tendrá el nombre de archivo "**RTC.calls. `[UTC date]` . csv**" y direct routing "**DirectRouting.calls. `[UTC date]` . csv**".

 Además de los archivos de enrutamiento directo y RTC, el archivo contiene el archivo **"parameters.js**", con el intervalo de tiempo de exportación seleccionado y las capacidades.

Los archivos exportados están en formato de valores separados por comas (CSV), que cumplen con [el estándar RFC 4180.](https://tools.ietf.org/html/rfc4180) Los archivos se pueden abrir en Excel o en cualquier otro editor que cumpla con los estándares sin que sea necesario realizar transformaciones.

La primera fila del ARCHIVO CSV contiene los nombres de columna. Todas las fechas son UTC y están [en formato ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Informe de uso de RTC exportado

 Puede exportar datos hasta un año desde la fecha actual, a menos que las normativas específicas del país prohíban la conservación de los datos durante 12 meses.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador único de llamada |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | Id. de la audioconferencia |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Llamar al id. de usuario en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente es la misma que la dirección SIP del usuario y puede ser la misma que la dirección de correo electrónico del usuario |
> | 6 | Nombre para mostrar de usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que recibió la llamada para llamadas entrantes o el número marcado para las llamadas salientes. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de llamada | `nvarchar(32)` | Si la llamada era una llamada entrante o saliente con RTC y el tipo de llamada, como una llamada realizada por un usuario o una audioconferencia |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | 10 | Nacional/Internacional | `nvarchar(16)` | Si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | 11 | Destino marcado | `nvarchar(64)` | País o región marcados |
> | 12 | Número de destino | `nvarchar(32)` | Número marcado en [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de la llamada |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada |
> | 15 | Duration Seconds | `int` | Cuánto tiempo estuvo conectada la llamada |
> | 16 | Tarifa de conexión | `numeric(16, 2)` | Precio del cargo por conexión |
> | 17 | Cargar | `numeric(16, 2)` | Cantidad de dinero o coste de la llamada que se cargará a tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda usada para calcular el costo de la llamada[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funcionalidad | `nvarchar(32)` | La licencia usada para la llamada |

### <a name="exported-direct-routing-usage-report"></a>Informe de uso de enrutamiento directo exportado

Puede exportar datos hasta cinco meses (150 días) desde la fecha actual, a menos que las normativas específicas del país prohíban la conservación de los datos durante ese período.

> [!div class="has-no-wrap"]  
> | # | Nombre | [Tipo de datos (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificador único de llamada |
> | 1 | Dirección SIP | `nvarchar(128)` | La dirección del usuario o bot que realizó o recibió la llamada.<br/>Tenga en cuenta que se trata en realidad de UserPrincipalName (UPN, nombre de inicio de sesión) en Azure Active Directory, que normalmente es el mismo que la dirección SIP |
> | 2 | Nombre para mostrar | `nvarchar(128)` | El nombre de un usuario o un bot de llamada (por ejemplo, cola de llamadas o Operador automático) establecido en el Centro de administración de Microsoft 365 |
> | 3 | País de usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Hora de invitación | `datetimeoffset` | Cuando la invitación inicial se envía de salida desde un usuario de Teams o una llamada bot al SBC, o cuando se recibe en la llamada entrante a Teams o bot por el componente proxy SIP de enrutamiento directo desde la SBC |
> | 5 | Hora de inicio | `datetimeoffset` | Hora en la que el proxy SIP ha recibido la respuesta final (mensaje SIP "200 Ok") desde el SBC de salida (Equipos/Bot a un usuario RTC), o después de que el proxy SIP envíe la invitación al próximo salto dentro del back-end de Teams en las llamadas entrantes (usuario de RTC a un equipo/bot).<br/>En el caso de llamadas con errores o sin responder, puede ser igual a invitación o tiempo de error |
> | 6 | Tiempo de error | `datetimeoffset` | Solo existe para llamadas con errores (no establecidos completamente) |
> | 7 | Hora de finalización | `datetimeoffset` | Solo existe para llamadas correctas (establecidas completamente). Hora en la que la llamada finalizó |
> | 8 | Duración (segundos) | `int` | Duración de la llamada |
> | 9 | Correcto | `nvarchar(3)` | Sí/No. Éxito o intento |
> | 10 | Número de autor de la llamada | `nvarchar(32)` | Número del usuario o bot que realizó la llamada. Al llamar a un usuario de equipo, será un usuario de RTC, al salir de la llamada del usuario de Teams, será el número de usuario de Teams. |
> | 12 | Número del destinatario | `nvarchar(32)` | Número del usuario o bot que ha recibido la llamada. Al llamar a un usuario de equipo, será el usuario de Teams, al salir de la llamada del usuario de Teams, será el usuario de RTC. |
> | 13 | Tipo de llamada | `nvarchar(32)` | Tipo y dirección de la llamada |
> | 14 | Región de Azure para medios | `nvarchar(8)` | El centro de datos usado para la ruta de acceso a medios en una llamada que no es de omisión |
> | 15 | Región de Azure para señalización | `nvarchar(8)` | El centro de datos usado para la señalización para llamadas de omisión y de no omisión |
> | 16 | Código SIP final | `int` | El código con el que finalizó la llamada, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Subcodificación final de Microsoft | `int` | Además de los códigos SIP, Microsoft tiene subcódigos propios que indican el problema específico |
> | 18 | Frase SIP final | `nvarchar(256)` | Descripción del código SIP y el subcódigo de Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nombre de dominio completo del controlador de borde de sesión |
> | 20 | Omisión de medios | `nvarchar(3)` | Sí/No. Indica si el tronco se habilitó para la omisión de medios o no |
> | 21 | Id. de correlación compartida | `uniqueidentifier` | Indica que dos o más llamadas están relacionadas |


## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
