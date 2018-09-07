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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: El nuevo panel Informes de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto.
ms.openlocfilehash: 46a44a61777cdd4d52b9899429b4a17ffe6ad7cb
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851813"
---
# <a name="session-details-report"></a>Informe de detalles de la sesión

[] El nuevo panel **Informes** de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto. Por ejemplo, puede usar el informe de **Skype para detalles de la sesión de negocio** para ver detalles acerca de las experiencias de llamada de usuario individual.
  
Consulte [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes que están disponibles.
  
Este informe, junto con los otro Skype para informes de negocios proporcionan detalles sobre actividad, incluidos los detalles de la sesión en toda la organización. Estos detalles son muy útiles cuando se investigar, planear y realizar otros profesionales las decisiones durante la para su organización y para la configuración de [comunicaciones créditos](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Cómo llegar a la Skype para el informe de detalles de sesiones de negocio

1. Vaya al **Centro de administración de Office 365** > **informes**
    
2. Seleccione **informes** en el menú de la izquierda y, a continuación, haga clic en **uso**.
    
3. En la lista **Seleccione un informe**, haga clic en **Skype para detalles de la sesión de negocio**.
    
    > [!TIP]
    > Si no ve este informe enumerado, vaya a **Skype para el centro de administración de negocio** > **informes** > **Detalles de la sesión**. 
  
    > [!IMPORTANT]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar el Skype para el informe de detalles de sesiones de negocio

Puede obtener una vista en Skype del usuario para obtener información detallada de negocio sesión mirando en cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Skype para el panel de informe de detalles de sesiones de negocio.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Usuario de búsqueda por alias** le permite buscar un único usuario y todos los detalles de la sesión del usuario muestran en la tabla siguiente. 
***
![Número 2](../images/sfbcallout2.png)<br/>**ENTRAR desde fecha hora** permite que poner en la fecha de inicio. Puede usar el calendario para seleccionar la fecha o especifique la fecha de forma manual. Este campo se debe rellenar.
***
![Número 3](../images/sfbcallout3.png)<br/>**ENTRAR para fecha hora** permite que poner en la fecha de finalización. Puede usar el calendario para seleccionar la fecha o especifique la fecha de forma manual. Si no se establece fecha de finalización, el valor predeterminado es 30 días desde la fecha de inicio.
***
![Número 4](../images/sfbcallout4.png)<br/>La tabla muestra un desglose de los todos los detalles de la sesión por usuario. Muestra todos los usuarios que tienen Skype para la empresa asignada a ellas y su información de la sesión. Puede agregar o quitar columnas en la tabla. <br/><br/>La tabla tiene las columnas siguientes para cada sesión:
*    **Identificador de diálogo** es el identificador de identificador único de la sesión SIP.
*    **Descripción de tipos de medios** describe si la sesión es una llamada de conferencia o una sesión de P2P y el tipo de medios utilizados (uso compartido de Audio, vídeo o aplicación).
*    **Hora de inicio** es la hora en la que inició la sesión.
*    **Hora de finalización** es la hora en que finalizó la sesión.
*    **Identificador URI desde** es el URI del usuario o servicio que inició la sesión. Puede estar en blanco si el usuario inició la sesión desde un teléfono RTC.
*    **A URI** es el URI del usuario o servicio que era el destino del inicio de sesión. En el caso de la conferencia, se trata URI del organizador de la. Puede estar en blanco si el destino de la sesión era un número de teléfono RTC.
*    **Desde la versión de cliente** indica el agente de usuario y la versión del cliente usado por el usuario o el servicio que inició la sesión.
*    **Para la versión de cliente** indica el agente de usuario y la versión del cliente usado por el usuario o el servicio que era el destino del inicio de sesión.
*    **Dirección URL de conferencia** es la dirección URL de SIP para la conferencia, si la sesión era una llamada de conferencia. Todos los usuarios en la misma llamada de conferencia tendrán la misma dirección URL de conferencia. 
*    **Número de teléfono** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono que se pueden reemplazar por 'x' para proteger la privacidad del usuario.
*    **Número de teléfono a** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono que se pueden reemplazar por 'x' para proteger la privacidad del usuario.
*    **Identificador de extremo** es un GUID único del extremo usado por el usuario de From. Se usa para identificar si el usuario que está comunicando varias sesiones del mismo extremo. Puede estar en blanco si el usuario está utilizando un teléfono RTC o si no ha iniciado la sesión de un servicio.
*    **Para el identificador del extremo** es un GUID único del extremo usado por el usuario a. Se usa para identificar si el usuario que está comunicando varias sesiones del mismo extremo. Puede estar en blanco si el usuario está utilizando un teléfono RTC, si se inició la sesión de un servicio o no se pudo establecer una sesión.
*    **Instancia de conf** es un GUID único para la instancia de la conferencia utilizando la dirección URL de la conferencia. Las reuniones periódicas tendrán la misma dirección URL de conferencia, pero cada instancia de la reunión tendrá una diferencia instancia Conf.
*    **En nombre de URI** es el URI del usuario que ha delegado en cuyo nombre se está estableciendo la sesión. <br/> **Hace referencia mediante URI** es el URI del usuario que hace referencia el establecimiento de una sesión.
*    **Código de respuesta** es el código de respuesta SIP para el establecimiento de la sesión que indica si la sesión se ha establecido correctamente.

Para cada sesión, hay una tabla sub con datos diferentes disponibles en función del escenario. A continuación enumeran las fichas disponibles en la tabla sub para el campo de y a usuario o servicios.
*    Ficha de sesión muestra datos acerca de los equipos y sistemas operativos.
*    Ficha MEDIALINES muestra información de conectividad de red y la información del dispositivo.
*    Ficha AUDIOSTREAMS muestra los datos de rendimiento de red acerca de las secuencias de audio implicados en la sesión.
*    Ficha AUDIOCLIENTEVENTS muestra datos acerca de los problemas de cliente detectada afecta a la experiencia de audio.
*    Ficha AUDIOSIGNALS muestra datos acerca de la señal de audio de procesamiento para la sesión.
*    APPSHARINGSTREAMS ficha muestra datos de rendimiento de red sobre el uso compartido de aplicaciones o secuencias de uso compartidas de escritorio implicados en la sesión.
*    Ficha VIDEOCLIENTEVENTS muestra datos acerca de los problemas de cliente detectada afecta a la experiencia de vídeo.
*    Ficha VIDEOSTREAMS muestra los datos de rendimiento de red acerca de las secuencias de vídeo implicados en la sesión.
*    Ficha TRACEROUTES muestra los saltos de red que se recopilan a través de traceroute durante la sesión. La ruta de acceso de medios reales que se usará para la sesión puede variar y estos datos sólo están disponibles cuando no hay audio en la sesión.
*    Ficha FEEDBACKREPORTS muestra cualquier final de datos de la encuesta llamada proporcionados por los usuarios en la sesión.
***
![Número 5](../images/sfbcallout5.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 6](../images/sfbcallout6.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para informe de actividad de negocio](activity-report.md) Puede ver la cantidad de los usuarios están usando peer-to-peer, organizada y participó en las sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede para ver los dispositivos incluidos los sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype para la aplicación empresarial de instalan y están usando para la mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de organizador de conferencia empresarial](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizar conferencias que utilizan mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, dial-in/out - 3rd fabricantes y dial-in/out - Microsoft.
    
- [Skype para informe de actividad de participantes de conferencia empresarial](conference-participant-activity-report.md) Puede ver cuántos de mensajería instantánea, audio y vídeo, compartir aplicaciones, Web y y conferencias de conferencia de acceso telefónico de entrada/salida se va a participó en.
    
- [Skype para informe de actividad de punto a punto de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype para el informe de uso de RTC de negocio](pstn-usage-report.md) Puede ver el número de minutos empleado en las llamadas de entrada y salida y el costo de estas llamadas.

- [Informe de bloqueados de Skype para usuarios profesionales](users-blocked-report.md) Puede ver los usuarios de la organización que se han bloqueado desde la realización de llamadas de RTC.

- [Skype para informe de grupos de servidores minuto RTC de negocio](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 