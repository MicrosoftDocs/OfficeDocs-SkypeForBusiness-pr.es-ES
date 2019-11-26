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
- M365-voice
description: Obtenga información sobre cómo usar el informe de uso de RTC de Teams en el centro de administración de Microsoft Teams para obtener información general sobre el uso de las llamadas y las conferencias de audio de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c91530af745a287198e99dbb83cd39257d978452
ms.sourcegitcommit: 4c763a3824e6a2271d98a46d25a03c8f04ee2f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257439"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Informe de uso de RTC de Microsoft Teams

El informe de uso de RTC de Teams en el centro de administración de Microsoft Teams le ofrece información general sobre las llamadas y las conferencias de audio de su organización. Puede ver la actividad de llamadas detalladas para los planes de llamadas si usa Microsoft como operador de telefonía y enrutamiento directo si usa su propio operador de telefonía.

La pestaña **planes de llamada** muestra la información que incluye el número de minutos que los usuarios han invertido en llamadas RTC entrantes y salientes, así como el costo de estas llamadas. La pestaña **enrutamiento directo** muestra información que incluye la dirección SIP y las horas de inicio y finalización de la llamada. Use la información de este informe para obtener información sobre el uso de RTC en su organización y ayudarle a investigar, planear y tomar decisiones empresariales.

## <a name="view-the-report"></a>Ver el informe

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**. En la pestaña **ver informes** , en **Informe**, seleccione **Informe de uso de RTC**.
2. En **intervalo de fechas**, seleccione un rango predefinido de 7 o 28 días, o establezca un rango personalizado y, a continuación, seleccione **Ejecutar Informe**.

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="calling-plans"></a>Planes de llamadas

![Captura de pantalla del informe de informe de uso de RTC de planes de llamada en el centro de administración](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de pantalla del informe de uso de RTC en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede visualizar para las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que haya establecido. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado. <br>Desplace el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla ofrece un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es el momento en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**Username** es el nombre de inicio de sesión del usuario.</li><li>**Número de teléfono** es el número que recibió la llamada de llamadas entrantes o el número marcado para llamadas salientes.</li><li>**Tipo de llamada** indica si la llamada fue una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Entre las llamadas que puede ver se incluyen las siguientes:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**user_in** : el usuario recibió una llamada RTC entrante.</li><li>**user_out** : el usuario colocó una llamada RTC saliente</li><li>**user_out_conf** : el usuario agregó dos o más participantes de la RTC a la llamada, como una llamada de conferencia de tres vías</li><li>**user_out_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**user_out_forwarding** : el usuario ha desviado la llamada a un número RTC</li><li>**conf_in** : una llamada entrante al puente de audioconferencia</li><li>**conf_out** : una llamada saliente del puente de conferencias de audio suele agregar un número RTC a la Conferencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**ucap_in** : una llamada RTC entrante a un bot de Teams, como un operador automático o una cola de llamadas</li><li>**ucap_out** : una llamada RTC saliente de un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado** es el número marcado.</li><li>**A país o región** es el país o la región marcados.</li><li>**Llamado** es el número que hizo la llamada.</li><li>**Desde país o región** es el país o la región desde donde se realizó la llamada.</li><li>**Cargo** es la cantidad de dinero o coste de la llamada que se cobra a tu cuenta. </li><li>**Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. </li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Nacional/internacional** le indica si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario.</li><li>El **identificador de llamada** es el identificador de llamada de una llamada. Es un identificador único de la llamada que puede usar al llamar al soporte técnico de Microsoft.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**País o región** es la ubicación de uso. </li> <li>El **identificador de conferencia** es el identificador de conferencia de la Conferencia de audio. </li><li>**Capacidad** es la licencia que se usa para la llamada. Entre los tipos de licencia que puede ver se incluyen:<ul><li>**MCOPSTNPP** -créditos de comunicaciones</li><li>Plan de llamadas **MCOPSTN1** -nacionales (3000 min Estados unidos/1200 mín. planes de la UE)</li><li>Plan de llamadas **MCOPSTN2** -International</li><li>Plan de llamadas **MCOPSTN5** -nacionales (120)</li><li>Plan de llamadas **MCOPSTN6** -nacionales (240)</li><li>**MCOMEETADD** : audioconferencia</li><li>Videoconferencias por minuto de **MCOMEETACPEA**</li></ul></li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **filtro** para filtrar el informe por nombre de usuario o llamada |
|**7**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa. |
|**4,8**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.|

### <a name="direct-routing"></a>Enrutamiento directo

![Captura de pantalla del informe de uso del informe de uso de RTC de enrutamiento directo en el centro de administración](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de pantalla del informe de uso de RTC de enrutamiento directo en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe se puede visualizar para las tendencias de los últimos 7 días o 28 días. |
|**2**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número total de llamadas durante el período de tiempo seleccionado.<br>Desplace el puntero sobre el punto en una fecha determinada para ver el total de llamadas en esa fecha.  |
|**4**   |La tabla ofrece un desglose del uso de RTC por llamada. <ul><li>**Marca de tiempo (UTC)** es el momento en que se inició la llamada.</li><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams. El nombre también puede ser el nombre de un bot, por ejemplo, la cola de llamadas o el operador automático de la nube. </li><li>**Dirección SIP** es la dirección SIP del usuario o un bot que recibió o hizo la llamada.</li><li>**Número de llamadas** es el número del usuario o el bot que realizó la llamada. </li>><li>**Número de teléfono del destinatario** de la llamada es el número del usuario o del bot que recibió la llamada. En una llamada entrante a un usuario de equipo, será el usuario de Teams, en una llamada saliente de un usuario de equipos, será el usuario de la RTC. </li><li>**Tipo de llamada** indica si la llamada fue una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Entre los tipos de llamadas que puede ver se incluyen:<br><br>**Tipos de llamadas de usuario de Teams**<ul><li>**dr_in** : el usuario recibió una llamada RTC entrante</li><li>**dr_out** : el usuario colocó una llamada RTC saliente</li><li>**dr_out_user_conf** : el usuario agregó un participante de RTC a la llamada</li><li>**user_out_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**dr_out_user_forwarding** : el usuario ha desviado la llamada a un número RTC</li><li>**dr_out_user_transfer** : el usuario transfirió la llamada a un número RTC</li><li>**dr_emergency_out** : el usuario hizo una llamada de emergencia</li></ul><br>**Tipos de llamadas de bots de Teams**<ul><li>**dr_in_ucap** : una llamada RTC entrante a un bot de Teams, como un operador automático o una cola de llamadas</li><li>**dr_out_ucap** : una llamada RTC saliente de un bot de Teams, como un operador automático o una cola de llamadas</li></ul><br><li>**Llamado** es el número del usuario que recibió la llamada.</li><li>**Hora de inicio (UTC)** es la hora en que el proxy SIP recibió la respuesta final (mensaje sip "200 correcto") desde el SBC en una llamada saliente (Teams/bot a un usuario de la RTC) o después de que el proxy SIP envíe la invitación al siguiente salto dentro del back-end del equipo en una llamada entrante (usuario de RTC a un equipo o bot) </li><li>**Hora de invitación (UTC)** es la hora en que se envió la invitación inicial en una llamada saliente de una llamada de usuario o bot de Teams a la SBC, o recibida en una llamada entrante a un equipo o bot mediante el componente proxy SIP de enrutamiento directo desde la SBC.</li><li>**Hora de error (UTC)** es el tiempo durante el que se produjo un error en la llamada. Solo para llamadas fallidas. El código final del SIP, el subcódigo final de Microsoft y la frase SIP final proporcionan las razones por las que se ha producido un error en la llamada y pueden ayudarte con la solución de problemas. </li><li>**Hora de finalización (UTC)** es la hora de finalización de la llamada (solo para llamadas correctas).</li><li>**Duración** muestra el tiempo durante el cual ha estado conectada la llamada.</li><li>**Tipo de número** es el tipo de número de teléfono del usuario, como un servicio de número gratuito. </li><li>**Omisión de elementos multimedia** indica si el tronco se ha habilitado para la omisión de medios. </li> <li>El **FQDN de SBC** es el nombre de dominio completo (FQDN) del controlador de borde de sesión (SBC). </li><li>La **región de Azure para multimedia** es el centro de datos que se usó como ruta multimedia en una llamada sin derivar. </li><li>La **región de Azure para la señalización** es el centro de datos que se usó para la señalización de llamadas de omisión y de no omisión. </li><li>**Tipo de evento** es el tipo de evento de la llamada. Verás el éxito de las llamadas realizadas y el intento de llamadas fallidas. </li><li>El **código de SIP final** es el código con el que ha finalizado la llamada.</li><li>El **subcódigo final de Microsoft** es un código que indica acciones específicas que se han producido.</li><li>La **frase final del SIP** es la descripción del código SIP y el subcódigo de Microsoft.</li><li>El **identificador de correlación** es un identificador único de la llamada que puede usar al llamar al soporte técnico de Microsoft.</li><li>El **identificador de correlación compartido** solo está visible en el archivo CSV que se puede descargar y no existe en el portal. El identificador de correlación compartido existe al menos en dos llamadas relacionadas. Consulta la descripción detallada a continuación.</li></ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa. |
|**7**   |Seleccione **exportar a Excel** para descargar los datos en un archivo delimitado por comas (CSV) para análisis sin conexión o para usarlo como entrada para su sistema de facturación. |

**Consideraciones sobre los campos llamador y destinatario**

En función de la dirección de la llamada, los nombres de los autores de llamadas o de los destinatarios pueden contener números no E164.

Estos campos pueden provenir de las SBC (s) de los clientes. Hay tres formatos que la SBC puede enviar al enrutamiento directo: E. 164 números, números no E. 164 y cadenas.

- E. 164 número de teléfono de un usuario que tiene un número E. 164 para un usuario que también tiene un número E. 164. 
- Llama desde un número no-E. 164. Un usuario de un PBX de terceros interconectado con enrutamiento directo hace una llamada a un usuario de Teams. En este caso, el número de la persona que llama puede ser cualquier número no-E. 164; por ejemplo, + 1001. 
- Un remitente de correo masivo llama y no presenta un número, solo un nombre, por ejemplo, "servicio de ingresos internos". Esta cadena se mostrará en los informes.

**Acerca del identificador de correlación compartida**

El identificador de correlación compartido solo existe en el archivo de Excel exportado que se descarga e indica que hay dos o más llamadas relacionadas. A continuación, se explican los diferentes escenarios y cuándo está presente el identificador de correlación compartido.

1.  Usuario de RTC 1 en un extremo de RTC denominado Teams User 1 en el cliente de Teams, llame a tipo Dr_In, Correlation ID 57f28917-42k5-4c0c-9433-79734873f2ac, sin identificador de correlación compartido.
2.  Teams usuario 1 en el cliente de Teams denominado RTC usuario 1 en un extremo de RTC, tipo de llamada Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sin identificador de correlación compartido.
3.  Usuario de RTC 1 en un extremo de RTC denominado Teams User 2 en el cliente de Teams, llame a tipo Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, Shared Correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.  Llamada existente 3 con identificación de correlación "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuario de RTC 1 en una llamada con el usuario de Teams 2. Equipo: el usuario 2 ha transferido (ciego o consultivo) una llamada a teams o a un usuario de RTC, llamada tipo Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de correlación compartida f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
