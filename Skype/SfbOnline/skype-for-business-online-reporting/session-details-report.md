---
title: Informe de detalles de la sesión
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: El nuevo panel Informes de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto.
ms.openlocfilehash: faee3d0a4f2228ddc32121bf85cc2f6b3018f2cc
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793066"
---
# <a name="session-details-report"></a>Informe de detalles de la sesión

[] El nuevo panel **Informes** de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto. Por ejemplo, puede usar el informe **detalles de sesión de Skype empresarial** para ver los detalles de las experiencias de llamadas de los usuarios individuales.
  
Consulte la [información general](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) de los informes para ver más informes que están disponibles.
  
Este informe, junto con los otros informes de Skype empresarial, ofrecen detalles sobre la actividad, incluidos los detalles de la sesión en toda la organización. Estos detalles son muy útiles para investigar, planear y tomar otras decisiones empresariales para su organización y para configurar [créditos de comunicaciones](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Puede ver todos los informes de Skype empresarial cuando inicia sesión como administrador en el centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Cómo acceder al informe detalles de sesión de Skype empresarial

1. Ir al centro de administración > **informes**
    
2. Seleccione **informes** en el menú de la izquierda y, a continuación, haga clic en **uso**.
    
3. En la lista que se muestra en **seleccionar un informe**, haga clic en **detalles de la sesión de Skype empresarial**.
    
    > [!TIP]
    > Si no ve este informe en la lista, vaya al >  **centro de administración de Skype empresarial****informes** > **detalles**de la sesión. 
  
    > [!IMPORTANT]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar el informe detalles de sesión de Skype empresarial

Puede obtener una vista de los detalles de la sesión de Skype empresarial de su usuario consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Detalles de la sesión de Skype empresarial panel de informes.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Buscar usuario por alias** le permite buscar un solo usuario y muestra todos los detalles de la sesión del usuario en la tabla siguiente. 
***
![Número 2](../images/sfbcallout2.png)<br/>**Introducir desde fecha hora** permite introducir la fecha de inicio. Puede usar el calendario para seleccionar la fecha o introducirla de forma manual. Este campo debe estar rellenado.
***
![Número 3](../images/sfbcallout3.png)<br/>**Entrar hasta fecha hora** permite especificar la fecha de finalización. Puede usar el calendario para seleccionar la fecha o introducirla de forma manual. Si no se establece ninguna fecha de finalización, el valor predeterminado es 30 días desde la fecha de inicio.
***
![Número 4](../images/sfbcallout4.png)<br/>En la tabla se muestra un desglose de todos los detalles de la sesión por usuario. Se muestran todos los usuarios que tienen Skype empresarial asignado y su información de sesión. Puede agregar o quitar columnas en la tabla. <br/><br/>La tabla tiene las siguientes columnas para cada sesión:
*    **Identificador de cuadro de diálogo** es el identificador del identificador único de la sesión SIP.
*    **Media Types Description** describe si la sesión es una llamada en conferencia o una sesión P2P y el tipo de medio usado (audio/vídeo/aplicación compartida).
*    La **hora de inicio** es la hora a la que se inició la sesión.
*    **Hora** de finalización es la hora de finalización de la sesión.
*    **From URI** es el identificador URI del usuario o servicio que inició la sesión. Puede estar en blanco si el usuario ha iniciado la sesión desde un teléfono PSTN.
*    **To URI** es el identificador URI del usuario o servicio que era el destino del inicio de sesión. En el caso de la Conferencia, este es el URI del organizador. Puede estar en blanco si el destino de la sesión era un número de teléfono RTC.
*    **Desde la versión de cliente** , se indica el agente de usuario y la versión del cliente que ha usado el usuario o servicio que inició la sesión.
*    La **versión de cliente** le indica el agente de usuario y la versión del cliente que ha usado el usuario o servicio que era el destino del inicio de la sesión.
*    **Dirección URL** de la Conferencia es la dirección URL del SIP de la Conferencia, si la sesión fue una llamada de conferencia. Todos los usuarios en la misma llamada en conferencia tendrán la misma dirección URL de conferencia. 
*    **Desde Tel** es el número de teléfono objetivo de la sesión, si corresponde. Los últimos dígitos del número de teléfono pueden sustituirse por ' x ' para proteger la privacidad del usuario.
*    **To Tel Number** es el número de teléfono objetivo de la sesión, si procede. Los últimos dígitos del número de teléfono pueden sustituirse por ' x ' para proteger la privacidad del usuario.
*    **Desde identificador de extremo** es un único GUID del extremo usado por el usuario de. Se usa para identificar si el usuario está comunicando varias sesiones desde el mismo punto de conexión. Puede estar en blanco si el usuario usa un teléfono PSTN o si la sesión se inició desde un servicio.
*    **Al identificador de extremo** es un único GUID del extremo usado por el usuario para. Se usa para identificar si el usuario está comunicando varias sesiones desde el mismo punto de conexión. Puede estar en blanco si el usuario usa un teléfono PSTN, si la sesión se inició desde un servicio o no se pudo establecer una sesión.
*    **Conf** es un GUID único para la instancia de la Conferencia mediante la dirección URL de la Conferencia. Las reuniones periódicas tendrán la misma dirección URL de conferencia, pero cada instancia de la reunión tendrá una instancia de la misma.
*    **En nombre de URI** es el URI del delegador en cuyo nombre se establece la sesión. <br/> El **URI** es el URI del usuario que se refiere al establecimiento de una sesión.
*    El **código de respuesta** es el código de respuesta SIP para el establecimiento de la sesión que indica si la sesión se estableció correctamente.

Para cada sesión, hay una subtabla con diferentes datos disponibles según el escenario. A continuación se enumeran las fichas disponibles en la subtabla para los usuarios de y a de, y a.
*    La pestaña sesión muestra datos sobre los equipos y los sistemas operativos.
*    La ficha MEDIALINES muestra información de conectividad de red e información del dispositivo.
*    La pestaña AUDIOSTREAMS muestra los datos de rendimiento de red sobre las transmisiones de audio implicadas en la sesión.
*    La pestaña AUDIOCLIENTEVENTS muestra datos sobre problemas detectados del cliente que afectan a la experiencia de audio.
*    La pestaña AUDIOSIGNALS muestra datos sobre el procesamiento de señal de audio para la sesión.
*    La pestaña APPSHARINGSTREAMS muestra los datos de rendimiento de red sobre las transmisiones uso compartido de aplicaciones o de escritorio que participan en la sesión.
*    La pestaña VIDEOCLIENTEVENTS muestra datos sobre problemas detectados del cliente que afectan a la experiencia de video.
*    La ficha Videostreams muestra los datos de rendimiento de red de las transmisiones de vídeo relacionadas con la sesión.
*    La ficha TRACEROUTE muestra los saltos de red recopilados mediante traceroute durante la sesión. La ruta de medios real que se usa para la sesión puede variar y estos datos solo están disponibles cuando hay audio en la sesión.
*    La ficha FEEDBACKREPORTS muestra los datos de la encuesta de llamadas proporcionados por los usuarios de la sesión.
***
![Número 5](../images/sfbcallout5.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 6](../images/sfbcallout6.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype empresarial?

- [Informe de actividad de Skype empresarial](activity-report.md) Puede ver cuánto están usando las sesiones de conferencia punto a punto, organizada y de participación.
    
- [Informe de uso de dispositivos de Skype empresarial](device-usage-report.md) Puede ver los dispositivos que incluyen sistemas operativos basados en Windows y dispositivos móviles que tienen instalada la aplicación Skype empresarial y la usan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype empresarial](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios las conferencias que usan la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones, la web, las llamadas entrantes/salientes y las llamadas entrantes y salientes de Microsoft.
    
- [Informe de actividad de participantes de conferencias de Skype empresarial](conference-participant-activity-report.md) Puede ver el número de participantes en conferencias de mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, Web y de llamadas entrantes y salientes.
    
- [Informe de actividad punto a punto de Skype empresarial](peer-to-peer-activity-report.md) Puede ver cuánto usan los usuarios la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de uso de RTC de Skype empresarial](pstn-usage-report.md) Puede ver la cantidad de minutos invertidos en llamadas entrantes o salientes, así como el coste de estas llamadas.

- [Informe de usuarios bloqueados de Skype empresarial](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.

- [Informe de grupos de minutos RTC de Skype empresarial](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes en curso en la organización.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 