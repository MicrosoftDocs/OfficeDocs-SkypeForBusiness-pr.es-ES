---
title: "Informe de detalles de la sesión"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Reporting
description: "El nuevo panel de mandos de Office 365 informes muestra el resumen de la actividad a través de los productos de Office 365 en su organización. Permite profundizar para informes del nivel de productos individuales para brindar información más detallada acerca de las actividades dentro de cada producto."
ms.openlocfilehash: be2cfb2c2e9d84c43fe31b49198381e0a2f9f483
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="session-details-report"></a>Informe de detalles de la sesión

El nuevo panel de mandos de Office 365 **informes** muestra el resumen de la actividad a través de los productos de Office 365 en su organización. Permite profundizar para informes del nivel de productos individuales para brindar información más detallada acerca de las actividades dentro de cada producto. Por ejemplo, puede utilizar el informe de **Skype para obtener detalles de la sesión de negocios** para ver detalles sobre experiencias de llamada del usuario individual.
  
Consulte [Resumen de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes que están disponibles.
  
Este informe, junto con lo otro Skype para informes empresariales proporcionan detalles sobre actividad, incluidos los detalles de la sesión a través de su organización. Estos detalles son muy útiles cuando usted investigando, planear y realizar otros negocios las decisiones para su organización y para la configuración de [comunicaciones créditos](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Cómo llegar a la Skype para informe de detalles de la sesión de negocios

1. Ir al **Centro de administración de Office 365** > **informes**
    
2. Seleccione **informes** en el menú de la izquierda y, a continuación, haga clic en **uso**.
    
3. En la lista **Seleccione un informe**, haga clic en **Skype para obtener detalles de la sesión de negocios**.
    
    > [!TIP]
    > Si no ve este informe aparece, vaya a **Skype para el centro de administración de negocios** > **informes** > **Detalles de la sesión**. 
  
    > [!IMPORTANT]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar el Skype para el informe de detalles de la sesión de negocios

Puede obtener una vista en Skype del usuario para los detalles de la sesión de negocios mirando en cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Skype para el tablero de mandos de negocios informe de detalles de sesión.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Usuario de búsqueda por alias** le permite buscar un usuario único y muestra todos los detalles de sesión del usuario en la tabla siguiente. 
***
![Número 2](../images/sfbcallout2.png)<br/>**ENTRAR desde fecha hora** permite que mostrar la fecha de inicio. Puede utilizar el calendario para seleccionar la fecha o escriba manualmente la fecha. Debe rellenar este campo.
***
![Número 3](../images/sfbcallout3.png)<br/>**ENTRAR a fecha hora** permite que mostrar en la fecha de finalización. Puede utilizar el calendario para seleccionar la fecha o escriba manualmente la fecha. Si no hay fecha final se establece, el valor predeterminado es 30 días desde la fecha de inicio.
***
![Número 4](../images/sfbcallout4.png)<br/>La tabla muestra un desglose de los todos los datos de sesión por usuario. Muestra todos los usuarios con Skype para empresa asignada y la información de sesión. Se pueden agregar o quitar columnas de la tabla. <br/><br/>La tabla tiene las columnas siguientes para cada sesión:
*    **Cuadro de diálogo ID** es el identificador de identificador único de la sesión SIP.
*    **Descripción de los tipos de medios** describe si la sesión es una llamada de conferencia o una sesión de P2P y el tipo de medio utilizado (Audio/vídeo/Application Sharing).
*    **Hora de inicio** es la hora en la que inició la sesión.
*    **Hora de finalización** es el tiempo cuando finalizó la sesión.
*    **De URI** es el identificador URI del usuario o servicio que inició la sesión. Puede estar en blanco si el usuario inició la sesión desde un teléfono RTC.
*    **A URI** es el identificador URI del usuario o servicio que era el destino de la iniciación de la sesión. En el caso de la conferencia, se trata URI del organizador de la. Puede estar en blanco si el destino de la sesión era un número de teléfono RTC.
*    **De versión del cliente** indica el agente de usuario y la versión del cliente utilizado por el usuario o el servicio Inicio de sesión.
*    **Para la versión del cliente** indica el agente de usuario y la versión del cliente utilizado por el usuario o el servicio que era el destino de la iniciación de la sesión.
*    **Dirección URL de la conferencia** es la dirección URL de SIP para la conferencia, si la sesión es una llamada de conferencia. Todos los usuarios en la misma llamada de conferencia tendrán la misma dirección URL de conferencia. 
*    **Número de teléfono** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono pueden sustituirse por 'x' para proteger la privacidad del usuario.
*    **Número de teléfono a** es el número de teléfono que era el destino de la sesión, si procede. Los últimos dígitos del número de teléfono pueden sustituirse por 'x' para proteger la privacidad del usuario.
*    **Identificador del extremo** es un GUID único del extremo utilizado por el usuario de From. Se utiliza para identificar si el usuario está comunicando varias sesiones del mismo extremo. Puede estar en blanco si el usuario está utilizando un teléfono PSTN o si la sesión se inició desde un servicio.
*    **Id de extremo** es un GUID único del extremo utilizado por el usuario a. Se utiliza para identificar si el usuario está comunicando varias sesiones del mismo extremo. Puede estar en blanco si el usuario está utilizando un teléfono PSTN, si inició la sesión de un servicio o no se pudo establecer una sesión.
*    **Instancia de conf** es un GUID único para la instancia de la conferencia utilizando la dirección URL de la conferencia. Las reuniones periódicas tendrán la misma dirección URL de conferencia, pero cada instancia de la reunión tendrán una diferencia instancia Conf.
*    **En nombre de URI** es el identificador URI de la persona que delega en cuyo nombre se está estableciendo la sesión. <br/> **A que se refiere al identificador URI** es el identificador URI del usuario que a que se refiere el establecimiento de una sesión.
*    **Código de respuesta** es el código de respuesta SIP para el establecimiento de la sesión que indica si la sesión se ha establecido correctamente.

Para cada sesión, hay una tabla sub con datos diferentes disponibles dependiendo del escenario. A continuación enumeran las fichas disponibles en la tabla de sub para el campo de y a usuarios o servicios.
*    Ficha de sesión muestra datos acerca de los equipos y sistemas operativos.
*    Ficha MEDIALINES muestra la información de conectividad de red y la información del dispositivo.
*    Ficha AUDIOSTREAMS muestra datos de rendimiento de la red acerca de las secuencias de audio implicados en la sesión.
*    Ficha AUDIOCLIENTEVENTS muestra datos acerca de los problemas de cliente detectado afectar a la experiencia de sonido.
*    Ficha AUDIOSIGNALS muestra datos acerca de la señal de audio de procesamiento para la sesión.
*    APPSHARINGSTREAMS ficha muestra datos de rendimiento de red sobre el uso compartido de aplicaciones o secuencias de uso compartidos de escritorio implicados en la sesión.
*    Ficha VIDEOCLIENTEVENTS muestra datos acerca de los problemas de cliente detectado afectar a la experiencia de vídeo.
*    Ficha VIDEOSTREAMS muestra datos de rendimiento de la red acerca de las secuencias de vídeo involucradas en la sesión.
*    Ficha TRACEROUTES muestra los saltos de red recogidos vía traceroute durante la sesión. La ruta de acceso de medios real utilizado para la sesión puede variar y estos datos sólo están disponibles cuando no hay audio en la sesión.
*    Ficha FEEDBACKREPORTS muestra cualquier final de datos de la encuesta de llamada proporcionados por los usuarios en la sesión.
***
![Número 5](../images/sfbcallout5.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 6](../images/sfbcallout6.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para el informe de la actividad de negocio](activity-report.md) Puede ver cuánto los usuarios utilizan peer-to-peer, organizada y participó en sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede ver los dispositivos incluyendo sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype para el negocio de la aplicación instalada y lo utilizan para mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de negocio conferencia multimedia](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizando las conferencias que utilizan mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, dial-in/out - 3ª parte y el dial-in/out - Microsoft.
    
- [Skype para informe de actividad de participantes de conferencia de negocio](conference-participant-activity-report.md) Puede ver cuántos de mensajería instantánea, audio o vídeo, compartir aplicaciones, Web y y conferencias conferencia dial-in/out están siendo participó en.
    
- [Skype para informe de actividad de igual a igual de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype para el informe de uso del negocio PSTN](pstn-usage-report.md) Puede ver el número de minutos dedicado a llamadas de entrada y de salida y el costo para estas llamadas.

- [Skype para usuarios de negocios bloqueado informe](users-blocked-report.md) Puede ver los usuarios de su organización que le impide realizar llamadas PSTN.

- [Skype para informe de minuto grupos empresariales PSTN](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
