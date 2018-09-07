---
title: Informe de actividad
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: d13ca7f70880d7ad0f3c6376e167c6222682887d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855579"
---
# <a name="activity-report"></a>Informe de actividad

[] El nuevo panel **Informes** de Office 365 muestra la información general de actividad en los productos de Office 365 de su organización. Permite que aumentar el detalle los informes de nivel de producto individuales a proporciona una idea más granular acerca de las actividades dentro de cada producto. Por ejemplo, puede usar el informe de **Skype para la actividad de negocio** para ver la cantidad de los usuarios están usando a peer-to-peer u organizado las sesiones de conferencia, o cuánto está que participan en sesiones de conferencia. 

Revise la [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más información.
  
Este informe, junto con los otro Skype para los informes de negocio, proporciona detalles sobre la actividad en toda la organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización.
  
> [!NOTE]
> Puede ver todos los Skype para informes de negocio cuando se inicia sesión como administrador en el centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Cómo acceder al informe de actividad de Skype Empresarial

1. Vaya al **Centro de administración de Office 365** > **informes** > **uso**.
    
2. En la página de **uso** , haga clic en **Skype para la actividad de negocio** en el **Seleccione una lista de informes** a la izquierda o haga clic en el widget de **Skype para la actividad de negocio** .
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Dependiendo de la suscripción a Office 365 que tiene, no es posible que vea todos los productos y los informes que se muestra aquí. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar el informe de actividad de Skype Empresarial

Puede obtener una vista de la actividad de Skype Empresarial de su usuario consultando los gráficos **Actividad** y **Usuarios**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
Puede verse el informe de actividad de correo electrónico de **Skype para la actividad de negocio** para las tendencias durante los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un día determinado en el informe, (vea número 7) mostrará la tabla de datos de hasta 28 días desde la fecha actual (no la fecha que se generó el informe).

> [!NOTE]
> Si hace clic en los detalles de un día específico, en la tabla sólo muestra los datos de los 30 días hasta la fecha de cuando se generó el informe.

***
![Número 2](../images/sfbcallout2.png)<br/>
Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 a 48 horas de tiempo de actividad. 
***
![Número 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número de actividades de conferencia que se están llevando a cabo en su organización. Le mostrará el número total y los tipos de sesiones **Punto a punto**, **Organizadas** y **Participadas** en las sesiones de conferencia de toda su organización.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Utilice los datos del gráfico interactivo **Usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades de conferencia realizadas en su organización. Mostrará el número total de usuarios junto con los tipos de **sesiones de punto a punto**, **organizada**y **Participated** en las sesiones de conferencia.
***
![Número 5](../images/sfbcallout5.png)<br/>
Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el diagrama de **actividad** , haga clic en o puntee en **las sesiones de punto a punto**, **organizado**o **Participated** para ver sólo la información relacionada con cada uno de ellos. Si se cambia esta selección, no se cambia la información en la tabla de cuadrícula. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical).
*    En el diagrama de **actividad** , el eje Y es el número total de punto a punto, organizan y participado en sesiones de conferencia que se conservan.
*    En el gráfico de actividad de **los usuarios** , el eje Y es el número de usuarios únicos asistir a cada tipo de punto a punto, organizan y participó en la conferencia.

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
La tabla muestra un desglose de todas las actividades de conferencia por usuario. Muestra todos los usuarios que disponen de Skype para la empresa asignada a ellas y sus actividades de conferencia. Puede agregar columnas adicionales a la tabla.
*    **Nombre de usuario** es el nombre del usuario.
*    **Eliminado** indica que se ha quitado la licencia del usuario.<br/><br/>
    > [!NOTE]
    > Actividad para un usuario eliminado seguirá mostrándose en un informe como navegará se concede bajo licencia en algún momento durante el período de tiempo seleccionado. La columna **Eliminado** ayuda a ver que el usuario ya no está activo, pero que ha contribuido a los datos del informe.
     
*    **Fecha de eliminación** es la fecha en que se quitó la licencia del usuario.
*    **Fecha de última actividad (UTC)** es la última vez que el usuario interactuó en una sesión de punto a punto u organizó una conferencia o participó en ella.
*    **Punto a punto** se muestra el número total de sesiones de conferencia de punto a punto que usa el usuario.
*    **Conferencias organizadas** muestra el número total de conferencias que ha organizado el usuario.
*    **Conferencias participadas** muestra el número total de conferencias en que ha participado el usuario.
*    **Producto asignado** hace referencia a los productos de Office 365 asignados a este usuario.<br/>

Si las directivas de su organización impiden la visualización de informes donde es identificable información de usuario, puede cambiar la configuración de privacidad para todos estos informes. Consulte la sección **ocultar los detalles de usuario en los informes** en los [Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8](../images/sfbcallout8.png)<br/>
Haga clic o puntee en el icono de **columnas** en cualquiera de las columnas para agregar o quitar columnas del informe.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Skype para el botón Exportar informes de negocio.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 a los usuarios, puede ordenar y filtrar dentro de la tabla en el informe de sí mismo. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede para ver los dispositivos, incluidos los sistemas operativos basados en Windows y dispositivos móviles, que tienen el Skype para la aplicación empresarial de instalan y están usando para la mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de organizador de conferencia empresarial](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizar conferencias que utilizan mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, dial-in/out - 3rd fabricantes y dial-in/out - Microsoft.
    
- [Skype para informe de actividad de punto a punto de negocio](peer-to-peer-activity-report.md) Puede ver la cantidad de los usuarios están usando aplicaciones de mensajería instantánea, audio y vídeo, uso compartido y la transferencia de archivos.
    
- [Informe de bloqueados de Skype para usuarios profesionales](users-blocked-report.md) Puede ver los usuarios de la organización que se han bloqueado desde la realización de llamadas de RTC.
    
- [Skype para el informe de uso de RTC de negocio](pstn-usage-report.md) Puede ver el número de minutos empleado en las llamadas de entrada y salida y el costo de estas llamadas.

- [Skype para informe de grupos de servidores minuto RTC de negocio](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.

- [Skype para el informe de detalles de sesiones de negocio](session-details-report.md) Puede ver detalles acerca de las experiencias de llamada de usuario individual.

    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
