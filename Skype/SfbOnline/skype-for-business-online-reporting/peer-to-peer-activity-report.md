---
title: Peer-to-peer activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: ad2e9745d68a3c47e60aa03f957054a1eeef1deb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="peer-to-peer-activity-report"></a>Peer-to-peer activity report

[] El nuevo panel **Informes** de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Le permite explorar los informes de nivel de cada producto para obtener datos más pormenorizados sobre las actividades dentro de cada producto. For example, you can use the **Skype for Business peer-to-peer activity** report to see how much your users are using IM, audio, video, application sharing, and transferring files. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización. 
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Cómo acceder al informe de actividad punto a punto de Skype Empresarial

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business peer-to-peer activity** on the **Select a report list** on the left. Or, click the **Skype for Business activity** widget and then click **Skype for Business peer-to-peer activity** on the **Skype for Business activity** list.
    
     ![Skype peer to peer menu selected](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes de actividad que se muestran en aquí. 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Interpretar el informe de actividad punto a punto de Skype Empresarial

Puede obtener una vista de su actividad punto a punto de Skype Empresarial en los gráficos **Actividad**, **Usuarios** y **Minutos**.
  
![Skype peer to peer report with callouts.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Number 1](../images/sfbcallout1.png)<br/>El informe de **actividad punto a punto de Skype Empresarial** se puede usar para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>Cada informe tiene la fecha del momento en que se generó. The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número total de sesiones por tipo de sesión que se realizan en su organización. It will show you the total number and types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** sessions across your organization. 
***
![Number 4](../images/sfbcallout4.png)<br/>Utilice los datos del gráfico interactivo **Usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades punto a punto realizadas en su organización. It will show you the total number of users along with the types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** in peer-to-peer sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>Utilice los datos del gráfico interactivo **Minutos** para comprender las tendencias de uso y ver el número de minutos utilizados por los usuarios al realizar actividades de punto a punto con audio y vídeo. Muestra el número total de minutos de **Audio** y **Vídeo** que se utilizan en las sesiones de punto a punto. 
***
![Number 6](../images/sfbcallout6.png)<br/>Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical). 
*    En el gráfico de actividad **Actividad**, el eje Y es el número total de sesiones de MI, audio, vídeo, uso compartido de aplicaciones y transferencia de archivos que han realizado sus usuarios en su organización.
*    On the **Users** activity chart, the Y axis is the total number users that held IM, audio, video, application sharing, and transferring files sessions. 
*    En el gráfico de actividad **Minutos**, el eje Y es el número total de minutos que han pasado los usuarios de su organización en sesiones de punto a punto de audio y vídeo. 

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.
***
![Number 7](../images/sfbcallout7.png)<br/>Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. For example, on the **Activity** chart, click or tap **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** to see only the info related to each one. Si se cambia esta selección, no se cambia la información en la tabla de cuadrícula. 
***
![Number 8](../images/sfbcallout8.png)<br/>La tabla muestra un desglose de todas las actividades de punto a punto por usuario. Se muestran todos los usuarios que tienen Skype Empresarial asignado y sus actividades de punto a punto. Puede agregar columnas a la tabla.
*    **Nombre de usuario** es el nombre del usuario.
*    **Eliminado** indica que se ha quitado la licencia del usuario. <br/> <br/> **Note:**  Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. La columna **Eliminado** ayuda a ver que el usuario ya no está activo, pero que ha contribuido a los datos del informe.  <br/><br/>
*    **Fecha de eliminación** es la fecha en que se quitó la licencia del usuario. 
*    **Fecha de última actividad (UTC)** es la fecha de última actividad (UTC) del usuario.
*    **MI** muestra el número total de sesiones de punto a punto que ha utilizado el usuario.
*    **Audio** muestra el número total de sesiones de punto a punto en las que se ha utilizado audio.
*    **Vídeo** muestra el número total de sesiones de punto a punto en las que se ha utilizado vídeo.
*    **Uso compartido de aplicaciones** muestra el número total de sesiones de punto a punto de uso compartido de aplicaciones.
*    **Transferencias de archivos** muestra el total de sesiones de punto a punto de transferencia de archivos.
*    **Minutos de audio** muestra el número total de minutos de audio que se han usado en la organización. 
*    **Minutos de audio** muestra el número total de minutos de audio que se han usado en la organización. 

Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
***
![Number 9](../images/sfbcallout9.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.
***
![Number 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype for Business activity report](activity-report.md) You can see how much your users are using peer-to-peer, organized, and participated in conferencing sessions.
    
- [Skype for Business device usage report](device-usage-report.md) You can to see the devices including Windows-based operating systems and mobile devices that have the Skype for Business app installed and are using it for IM and meetings.
    
- [Skype for Business conference organizer activity report](conference-organizer-activity-report.md) You can see how much your users are organizing conferences that use IM, audio/video, application sharing, Web, dial-in/out - 3rd party, and dial-in/out - Microsoft.
    
- [Skype for Business conference participant activity report](conference-participant-activity-report.md) You can see how many IM, audio/video, application sharing, Web and and dial-in/out conferencing conferences are being participated in.
    
- [Skype for Business users blocked report](users-blocked-report.md) You can see the users in your organization that have been blocked from making PSTN calls.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.
    
- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.
    
## <a name="related-topics"></a>See also
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 