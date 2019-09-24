---
title: Informe de uso de RTC de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de RTC de Teams en el centro de administración de Microsoft Teams para obtener información general sobre el uso de las llamadas y las conferencias de audio de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3674759844cc268fc503f4f617e0d18d16914593
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131688"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Informe de uso de RTC de Microsoft Teams

El informe de uso de RTC de Teams en el centro de administración de Microsoft Teams le ofrece información general sobre las llamadas y las conferencias de audio de su organización. Puede ver la actividad de llamadas detalladas para los planes de llamadas si usa Microsoft como operador de telefonía y enrutamiento directo si usa su propio operador de telefonía.

La pestaña **planes de llamada** muestra la información que incluye el número de minutos que los usuarios han invertido en llamadas RTC entrantes y salientes, así como el costo de estas llamadas. La pestaña **enrutamiento directo** muestra información que incluye la dirección SIP y las horas de inicio y finalización de la llamada. Use la información de este informe para obtener información sobre el uso de RTC en su organización y ayudarle a investigar, planear y tomar decisiones empresariales.

## <a name="view-the-report"></a>Ver el informe

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**. En la pestaña **ver informes** , en **Informe**, seleccione **Informe de uso de RTC**.
2. En **intervalo de fechas**, seleccione un rango predefinido de 7 o 28 días, o establezca un rango personalizado y, a continuación, seleccione **Ejecutar Informe**.

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="calling-plans"></a>Planes de llamadas

![Captura de pantalla del informe de informe de uso de RTC de planes de llamada en el centro de administración] (../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de pantalla del informe de uso de RTC en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede visualizar para las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que haya establecido. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado. <br>Desplace el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla ofrece un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es el momento en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**Username** es el nombre de inicio de sesión del usuario.</li><li>**Número de teléfono** es el número que recibió la llamada de llamadas entrantes o el número marcado para llamadas salientes.</li><li>**Tipo de llamada** indica si la llamada fue una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Entre las llamadas que puede ver se incluyen las siguientes:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**user_in** : el usuario recibió una llamada RTC entrante.</li><li>**user_out** : el usuario ha colocado una llamada RTC saliente</li><li>**user_out_conf** : el usuario agregó dos o más participantes de la RTC a la llamada, como una llamada de conferencia de tres vías</li><li>**user_out_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**user_out_forwarding** : el usuario ha desviado la llamada a un número RTC</li><li>**conf_in** : una llamada entrante al puente de audioconferencia</li><li>**conf_out** : una llamada saliente desde el puente de conferencias de audio generalmente para agregar un número RTC a la Conferencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**ucap_in** : una llamada RTC entrante a un bot de Teams, como un operador automático o una cola de llamadas</li><li>**ucap_out** : una llamada RTC saliente de un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado** es el número marcado.</li><li>**A país o región** es el país o la región marcados.</li><li>**Llamado** es el número que hizo la llamada.</li><li>**Desde país o región** es el país o la región desde donde se realizó la llamada.</li><li>**Cargo** es la cantidad de dinero o coste de la llamada que se cobra a tu cuenta. </li><li>**Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. </li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Nacional/internacional** le indica si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario.</li><li>El **identificador de llamada** es el identificador de llamada de una llamada. Es un identificador único de la llamada que puede usar al llamar al soporte técnico de Microsoft.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**País o región** es la ubicación de uso. </li> <li>El **identificador de conferencia** es el identificador de conferencia de la Conferencia de audio. </li><li>**Capacidad** es la licencia que se usa para la llamada. Entre los tipos de licencia que puede ver se incluyen:<ul><li>**MCOPSTNPP** -créditos de comunicaciones</li><li>Plan de llamadas **MCOPSTN1** -nacionales (3000 min Estados unidos/1200 mín. planes de la UE)</li><li>Plan de llamadas **MCOPSTN2** -International</li><li>Plan de llamadas **MCOPSTN5** -nacionales (120)</li><li>Plan de llamadas **MCOPSTN6** -nacionales (240)</li><li>**MCOMEETADD** : audioconferencia</li><li>Videoconferencias por minuto de **MCOMEETACPEA**</li></ul></li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **filtro** para filtrar el informe por nombre de usuario o llamada |
|**7**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa. |
|**4,8**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.|

### <a name="direct-routing"></a>Enrutamiento directo

![Captura de pantalla del informe de uso del informe de uso de RTC de enrutamiento directo en el centro de administración] (../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de pantalla del informe de uso de RTC de enrutamiento directo en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede visualizar para las tendencias de los últimos 7 días o 28 días. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado.<br>Desplace el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla ofrece un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es el momento en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**Dirección SIP** es la dirección SIP del usuario que recibió o hizo la llamada.</li><li>**Número de teléfono** es el número del usuario que realizó la llamada. </li><li>**Tipo de llamada** indica si la llamada fue una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Entre las llamadas que puede ver se incluyen las siguientes:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**dr_in** : el usuario recibió una llamada RTC entrante</li><li>**dr_out** : el usuario ha colocado una llamada RTC saliente</li><li>**dr_out_user_conf** : el usuario agregó un participante de RTC a la llamada</li><li>**user_out_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**dr_out_user_forwarding** : el usuario ha desviado la llamada a un número RTC</li><li>**dr_out_user_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**dr_emergency_out** : el usuario realiza una llamada de emergencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**dr_in_ucap** : una llamada RTC entrante a un bot de Teams, como un operador automático o una cola de llamadas</li><li>**dr_out_ucap** : una llamada RTC saliente de un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado** es el número del usuario que recibió la llamada.</li><li>**Hora de inicio (UTC)** es la hora a la que se conecta la llamada.</li><li>**Hora de invitación (UTC)** es la hora en que se inició la llamada.</li><li>**Hora de error (UTC)** es el tiempo durante el que se produjo un error en la llamada. (Solo para llamadas fallidas).</li><li>**Hora de finalización (UTC)** es la hora de finalización de la llamada. (Solo para llamadas correctas).</li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**Omisión de elementos multimedia** que indica si el tronco se ha habilitado para la omisión de medios </li> <li>El **FQDN de SBC** es el nombre de dominio completo (FQDN) del controlador de borde de sesión (SBC). </li><li>La **región de Azure** es el centro de recursos usado para la señalización.</li><li>**Tipo de evento** es el tipo de evento de la llamada. Verás el éxito de las llamadas realizadas y el intento de llamadas fallidas. </li><li>El **código de SIP final** es el código con el que ha finalizado la llamada.</li><li>El **subcódigo final de Microsoft** es un código que indica acciones específicas que se han producido.</li><li>La **frase final del SIP** es la descripción del código SIP y el subcódigo de Microsoft.</li><li>**Identificador de coorelse** es un identificador único para la llamada que puede usar al llamar al soporte técnico de Microsoft.</li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa. |

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)