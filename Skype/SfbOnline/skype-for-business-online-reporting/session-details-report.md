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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: El panel Informes muestra la información general de la actividad de los productos de Microsoft 365 u Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto.
ms.openlocfilehash: 951f93aabe66bdb7e6b92f9b2c6cf1627e7e1a10
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205511"
---
# <a name="session-details-report"></a>Informe de detalles de la sesión

El **panel** Informes muestra la información general de la actividad de los productos de Microsoft 365 u Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto. Por ejemplo, puede usar el informe detalles de la sesión de **Skype** Empresarial para ver detalles sobre las experiencias de llamada de un usuario individual.
  
Consulte información general [de los informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver más informes que están disponibles.
  
Este informe, junto con los demás informes de Skype Empresarial, le ofrece detalles sobre la actividad, incluidos los detalles de las sesiones en toda su organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización, así como para configurar [créditos de comunicaciones.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Cómo obtener el informe detalles de la sesión de Skype Empresarial

1. Ir al Centro de administración > **Informes**
    
2. Seleccione **Informes en** el menú izquierdo y, a continuación, haga clic en **Uso.**
    
3. En la lista que se **encuentra bajo Seleccionar un informe,** haga clic en Detalles de la sesión de Skype **Empresarial.**
    
    > [!TIP]
    > Si no ve este informe en la lista, vaya a los detalles de la sesión de informes del Centro de administración de **Skype**  >    >  **Empresarial.** 
  
    > [!IMPORTANT]
    > Según la suscripción a Microsoft 365 u Office 365 que tenga, es posible que no vea todos los productos e informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar el informe detalles de la sesión de Skype Empresarial

Puede obtener una vista de los detalles de la sesión de Skype Empresarial de su usuario consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Panel informe de detalles de la sesión de Skype Empresarial.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**La búsqueda de usuarios por alias** le permite buscar un único usuario y muestra todos los detalles de la sesión del usuario en la tabla siguiente. 
***
![Número 2](../images/sfbcallout2.png)<br/>**Escribir a partir de la hora** de la fecha le permite especificar la fecha de inicio. Puede usar el calendario para seleccionar la fecha o especificar la fecha manualmente. Este campo debe rellenarse.
***
![Número 3](../images/sfbcallout3.png)<br/>**Escribir la hora de fecha** le permite poner la fecha de finalización. Puede usar el calendario para seleccionar la fecha o especificar la fecha manualmente. Si no se establece ninguna fecha de finalización, el valor predeterminado es 30 días a partir de la fecha de inicio.
***
![Número 4](../images/sfbcallout4.png)<br/>La tabla muestra un desglose de todos los detalles de la sesión por usuario. Se muestran todos los usuarios que tienen Skype Empresarial asignado y la información de su sesión. Puede agregar o quitar columnas en la tabla. <br/><br/>La tabla tiene las siguientes columnas para cada sesión:
*    **Id. de** cuadro de diálogo es el identificador único de la sesión SIP.
*    **La descripción de los** tipos de medios describe si la sesión es una llamada de conferencia o una sesión P2P y el tipo de medio usado (audio/vídeo/uso compartido de aplicaciones).
*    **La hora de** inicio es la hora en que se inicia la sesión.
*    **La hora de** finalización es la hora a la que finalizó la sesión.
*    **Desde el URI** es el URI del usuario o servicio que inició la sesión. Puede estar en blanco si el usuario ha iniciado la sesión desde un teléfono RTC.
*    **Para URI** es el URI del usuario o servicio que fue el destino del inicio de sesión. En el caso de la conferencia, este es el URI del organizador. Puede estar en blanco si el destino de la sesión era un número de teléfono RTC.
*    **Desde la versión del** cliente se indica el agente de usuario y la versión del cliente usado por el usuario o servicio que inició la sesión.
*    **A la versión del** cliente se indica el Agente de usuario y la versión del cliente que ha usado el usuario o servicio objetivo del inicio de sesión.
*    **La dirección URL de** conferencia es la dirección URL del SIP para la conferencia, si la sesión era una llamada de conferencia. Todos los usuarios de la misma llamada de conferencia tendrán la misma dirección URL de conferencia. 
*    **Del número de teléfono** es el número de teléfono que fue el destino de la sesión, si procede. Los últimos dígitos del número de teléfono se pueden reemplazar por "x" para proteger la privacidad del usuario.
*    **A número de teléfono** es el número de teléfono objetivo de la sesión, si procede. Los últimos dígitos del número de teléfono se pueden reemplazar por "x" para proteger la privacidad del usuario.
*    **De Id. de** punto de conexión es un GUID único del punto de conexión que ha usado el usuario De. Se usa para identificar si el usuario comunica varias sesiones desde el mismo punto de conexión. Puede estar en blanco si el usuario usa un teléfono RTC o si la sesión se inició desde un servicio.
*    **Para el id. de** punto de conexión es un GUID único del punto de conexión que ha usado el usuario Para. Se usa para identificar si el usuario comunica varias sesiones desde el mismo punto de conexión. Puede que esté en blanco si el usuario usa un teléfono RTC, si la sesión se inició desde un servicio o si no se pudo establecer una sesión.
*    **La instancia de** conferencia es un GUID único para la instancia de la conferencia con la dirección URL de la conferencia. Las reuniones periódicas tendrán la misma dirección URL de conferencia, pero cada instancia de la reunión tendrá una instancia de conferencia diferente.
*    **En nombre del URI** es el URI del delegador en cuyo nombre se establece la sesión. <br/> **Referencia por URI es** el URI del usuario que hizo referencia al establecimiento de una sesión.
*    **Código de** respuesta es el código de respuesta SIP para el establecimiento de la sesión que indica si la sesión se ha establecido correctamente.

Para cada sesión, hay una subfila con datos diferentes disponibles según el escenario. A continuación, se enumeran las pestañas disponibles en la sub tabla para el usuario o servicios de origen y destino.
*    La pestaña SESIÓN muestra los datos sobre los equipos y sistemas operativos.
*    La pestaña MEDIALINES muestra la información de conectividad de red y la información del dispositivo.
*    La pestaña AUDIOSTREAMS muestra los datos de rendimiento de red sobre las transmisiones de audio involucradas en la sesión.
*    La pestaña AUDIOCLIENTEVENTS muestra los datos sobre problemas detectados por el cliente que afectan a la experiencia de audio.
*    La pestaña AUDIOSIGNALS muestra los datos sobre el procesamiento de la señal de audio para la sesión.
*    La pestaña APPSHARINGSTREAMS muestra los datos de rendimiento de red sobre las secuencias de uso compartido de aplicaciones o de escritorio compartida implicadas en la sesión.
*    La pestaña VIDEOCLIENTEVENTS muestra los datos sobre problemas detectados por el cliente que afectan a la experiencia de vídeo.
*    La pestaña SECUENCIAS DE VÍDEO muestra los datos de rendimiento de red sobre las transmisiones de vídeo implicadas en la sesión.
*    La pestaña TRACEROUTES muestra los saltos de red recopilados a través de traceroute durante la sesión. La ruta multimedia real usada para la sesión puede variar y estos datos solo están disponibles cuando hay audio en la sesión.
*    La pestaña FEEDBACKREPORTS muestra los datos de finalización de la encuesta de llamada proporcionados por los usuarios en la sesión.
***
![Número 5](../images/sfbcallout5.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 6](../images/sfbcallout6.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de actividad de Skype Empresarial](activity-report.md) Puede ver cuánto utilizan sus usuarios las sesiones de conferencia punto a punto, organizadas y participadas.
    
- [Informe de uso de dispositivos de Skype Empresarial](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación de Skype Empresarial instalada y que lo utilizan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype Empresarial](conference-organizer-activity-report.md) Puede ver cuánto utilizan sus usuarios las conferencias que utilizan la MI, el audio/vídeo, el uso compartido de aplicaciones, la Web, las llamadas locales (terceros) y las llamadas o salidas (Microsoft).
    
- [Informe de actividad de participantes de conferencias de Skype Empresarial](conference-participant-activity-report.md) Puede ver en cuántas conferencias de MI, audio/vídeo, uso compartido de aplicaciones, web y de acceso telefónico local/externo están participando los usuarios.
    
- [Informe de actividad punto a punto de Skype Empresarial](peer-to-peer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de uso de RTC de Skype Empresarial](pstn-usage-report.md) Puede ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas.

- [Informe de usuarios bloqueados de Skype Empresarial](users-blocked-report.md) Puede ver los usuarios de su organización a los que se les ha bloqueado la realización de llamadas RTC.

- [El informe de los grupos de](pstn-minute-pools-report.md) minutos RTC de Skype Empresarial permite ver el número de minutos consumidos durante el mes actual dentro de su organización.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 