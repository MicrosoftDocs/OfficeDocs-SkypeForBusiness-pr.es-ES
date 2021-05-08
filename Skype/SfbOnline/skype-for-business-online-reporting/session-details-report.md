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
description: En el panel Informes se muestra la información general sobre la actividad en Microsoft 365 o Office 365 productos de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto.
ms.openlocfilehash: 8b861cc863603a8ab51451e9906cd62313bd9cf9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238225"
---
# <a name="session-details-report"></a>Informe de detalles de la sesión

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En **el panel** Informes se muestra la información general sobre la actividad en Microsoft 365 o Office 365 productos de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto. Por ejemplo, puede usar el informe Skype Empresarial **detalles** de la sesión para ver detalles sobre las experiencias de llamada de un usuario individual.
  
Consulte Información [general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes disponibles.
  
Este informe, junto con los demás informes Skype Empresarial le ofrece detalles sobre la actividad, incluidos los detalles de la sesión en toda la organización. Estos detalles son muy útiles al investigar, planear y tomar otras decisiones empresariales para su organización y para configurar créditos [de comunicaciones.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes Skype Empresarial al iniciar sesión como administrador en el centro de Microsoft 365 administración. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Cómo obtener acceso al informe Skype Empresarial detalles de la sesión

1. Ir al Centro de administración > **Informes**
    
2. Seleccione **Informes en** el menú de la izquierda y, a continuación, haga clic en **Uso.**
    
3. En la lista en **Seleccionar un informe,** haga **clic Skype Empresarial detalles de la sesión.**
    
    > [!TIP]
    > Si no ve este informe en la lista, vaya a Skype Empresarial **de** sesión informes del Centro de  >    >  **administración.** 
  
    > [!IMPORTANT]
    > Dependiendo de Microsoft 365 o Office 365 suscripción que tenga, es posible que no vea todos los productos e informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar el informe Skype Empresarial detalles de la sesión

Puede obtener una vista de los detalles de la sesión Skype Empresarial usuario consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Skype Empresarial Panel Informe de detalles de la sesión.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Buscar usuario por alias** le permite buscar un único usuario y muestra todos los detalles de sesión del usuario en la tabla siguiente. 
***
![Número 2](../images/sfbcallout2.png)<br/>**Escribir a partir de la hora** de la fecha le permite colocar la fecha de inicio. Puede usar el calendario para seleccionar la fecha o escribir la fecha manualmente. Este campo debe rellenarse.
***
![Número 3](../images/sfbcallout3.png)<br/>**Escribir la hora de fecha** le permite poner la fecha de finalización. Puede usar el calendario para seleccionar la fecha o escribir la fecha manualmente. Si no se establece ninguna fecha de finalización, el valor predeterminado es 30 días a partir de la fecha de inicio.
***
![Número 4](../images/sfbcallout4.png)<br/>La tabla muestra un desglose de todos los detalles de la sesión por usuario. Esto muestra todos los usuarios que Skype Empresarial asignados a ellos y su información de sesión. Puede agregar o quitar columnas en la tabla. <br/><br/>La tabla tiene las siguientes columnas para cada sesión:
*    **Id. de** cuadro de diálogo es el id. de identificador único de la sesión SIP.
*    **Descripción de tipos de** medios describe si la sesión es una llamada de conferencia o una sesión P2P y el tipo de medios usados (audio/vídeo/uso compartido de aplicaciones).
*    **La hora de** inicio es la hora en la que se inició la sesión.
*    **La hora de** finalización es la hora en la que finalizó la sesión.
*    **Desde uri** es el URI del usuario o servicio que inició la sesión. Puede estar en blanco si el usuario inició la sesión desde un teléfono RTC.
*    **A URI** es el URI del usuario o servicio que era el destino del inicio de la sesión. En el caso de la conferencia, este es el URI del organizador. Puede estar en blanco si el destino de la sesión era un número de teléfono RTC.
*    **Desde la versión del cliente** se indica el Agente de usuario y la versión del cliente que usó el usuario o servicio que inició la sesión.
*    **A la versión del cliente** se le indica el Agente de usuario y la versión del cliente que usó el usuario o servicio que era el destino del inicio de la sesión.
*    **La dirección URL de** conferencia es la dirección URL SIP de la conferencia, si la sesión era una llamada de conferencia. Todos los usuarios de la misma llamada de conferencia tendrán la misma dirección URL de conferencia. 
*    **Desde Número de teléfono** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono se pueden reemplazar por "x" para proteger la privacidad del usuario.
*    **A Número de teléfono** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono se pueden reemplazar por "x" para proteger la privacidad del usuario.
*    **Del id. de** punto de conexión es un GUID único del punto de conexión usado por el usuario De. Se usa para identificar si el usuario comunica varias sesiones desde el mismo punto de conexión. Puede estar en blanco si el usuario usa un teléfono RTC o si la sesión se inició desde un servicio.
*    **To Endpoint Id** es un GUID único del punto de conexión usado por el usuario Para. Se usa para identificar si el usuario comunica varias sesiones desde el mismo punto de conexión. Puede estar en blanco si el usuario usa un teléfono RTC, si la sesión se inició desde un servicio o si no se pudo establecer una sesión.
*    **La instancia de Conf** es un GUID único para la instancia de la conferencia con la dirección URL de conferencia. Las reuniones periódicas tendrán la misma dirección URL de conferencia, pero cada instancia de la reunión tendrá una diferencia en la instancia de Conf.
*    **En nombre del URI** es el URI del delegado en cuyo nombre se establece la sesión. <br/> **Referred By URI** is the URI of the user who referred the establishment of a session.
*    **Código de respuesta** es el código de respuesta SIP para el establecimiento de la sesión que indica si la sesión se estableció correctamente.

Para cada sesión, hay una subclave con datos diferentes disponibles en función del escenario. A continuación se enumeran las pestañas disponibles en la sub tabla para el usuario o los servicios desde y para.
*    La pestaña SESIÓN muestra datos sobre los equipos y sistemas operativos.
*    La pestaña MEDIALINES muestra la información de conectividad de red y la información del dispositivo.
*    La pestaña AUDIOSTREAMS muestra los datos de rendimiento de red sobre las transmisiones de audio involucradas en la sesión.
*    La pestaña EVENTOSCLIENTE.AUDIO muestra datos sobre los problemas detectados por el cliente que afectan a la experiencia de audio.
*    La pestaña AUDIOSIGNALS muestra datos sobre el procesamiento de la señal de audio para la sesión.
*    La pestaña APPSHARINGSTREAMS muestra los datos de rendimiento de red sobre el uso compartido de aplicaciones o las transmisiones de uso compartido de escritorio involucradas en la sesión.
*    La pestaña VIDEOCLIENTEVENTS muestra datos sobre los problemas detectados por el cliente que afectan a la experiencia de vídeo.
*    La pestaña VIDEOSTREAMS muestra los datos de rendimiento de red sobre las transmisiones de vídeo involucradas en la sesión.
*    La pestaña TRACEROUTES muestra los saltos de red recopilados a través de traceroute durante la sesión. La ruta de acceso multimedia real usada para la sesión puede variar y estos datos solo están disponibles cuando hay audio en la sesión.
*    La pestaña FEEDBACKREPORTS muestra los datos de la encuesta de finalización de la llamada proporcionados por los usuarios en la sesión.
***
![Número 5](../images/sfbcallout5.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 6](../images/sfbcallout6.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros Skype Empresarial informes?

- [Skype Empresarial actividad](activity-report.md) Puede ver cuánto usan los usuarios de punto a punto, organizados y participados en sesiones de conferencia.
    
- [Skype Empresarial de uso de dispositivos](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación Skype Empresarial instalada y la usan para mensajería instantánea y reuniones.
    
- [Skype Empresarial actividad del organizador de conferencias](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios conferencias que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, Web, acceso telefónico/salida - terceros y acceso telefónico local / salida - Microsoft.
    
- [Skype Empresarial actividad de los participantes de la conferencia](conference-participant-activity-report.md) Puede ver cuántas conferencias de mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, conferencias web y de acceso telefónico local/externo están participando.
    
- [Skype Empresarial de actividad punto a punto](peer-to-peer-activity-report.md) Puede ver la cantidad de usuarios que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype Empresarial de uso de RTC](pstn-usage-report.md) Puede ver el número de minutos invertidos en llamadas entrantes y salientes y el costo de estas llamadas.

- [Skype Empresarial de usuarios bloqueados](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.

- [Skype Empresarial de grupos de minutos](pstn-minute-pools-report.md) RTC puede ver el número de minutos consumidos durante el mes actual dentro de su organización.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el Centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
