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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 1da7ea7b826d5a8f86691cda8b41b49298114d50
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692455"
---
# <a name="activity-report"></a>Informe de actividad

El panel de **informes** de Office 365 le muestra la información general de actividades en los productos de Office 365 de su organización. Le permite profundizar en informes individuales de nivel de producto para proporcionarle información más detallada sobre las actividades de cada producto. Por ejemplo, puede usar el informe de **actividad de Skype empresarial** para ver cuánto están usando las sesiones de conferencia de punto a punto o organizada o cuánto están participando en sesiones de conferencia. 

Consulte la [información general](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) de los informes para obtener más información.
  
Este informe, junto con los otros informes de Skype empresarial, le ofrece detalles sobre la actividad en toda su organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización.
  
> [!NOTE]
> Puede ver todos los informes de Skype empresarial cuando inicia sesión como administrador en el centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Cómo acceder al informe de actividad de Skype Empresarial

1. Vaya al centro de administración > **** > **uso**de informes.
    
2. En la **Página uso** , elija**actividad** de **Skype empresarial** > en la **lista seleccionar un informe** de la izquierda o haga clic en el widget de **actividad de Skype empresarial** .

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar el informe de actividad de Skype Empresarial

Puede obtener una vista de la actividad de Skype Empresarial de su usuario consultando los gráficos **Actividad** y **Usuarios**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
El informe actividad de correo electrónico de **actividad de Skype empresarial** se puede visualizar para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un día determinado del informe, la tabla (vea el número 7) mostrará datos durante un máximo de 28 días desde la fecha actual (no la fecha en la que se generó el informe).

> [!NOTE]
> Si hace clic en los detalles de un día específico, la tabla solo mostrará los datos de los 30 días hasta la fecha en la que se generó el informe.

***
![Número 2](../images/sfbcallout2.png)<br/>
Cada informe tiene la fecha del momento en que se generó. Por lo general, los informes reflejan una latencia de 24 a 48 horas de duración de la actividad. 
***
![Número 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número de actividades de conferencia que se están llevando a cabo en su organización. Le mostrará el número total y los tipos de sesiones **Punto a punto**, **Organizadas** y **Participadas** en las sesiones de conferencia de toda su organización.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Utilice los datos del gráfico interactivo **Usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades de conferencia realizadas en su organización. Le mostrará el número total de usuarios, junto con los tipos de **sesiones punto a punto**, **organizadas**y en las que **participó** en sesiones de conferencia.
***
![Número 5](../images/sfbcallout5.png)<br/>
Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el gráfico **actividad** , haga clic o pulse en **sesiones de punto a punto**, **organizadas**o **participadas** para ver solo la información relacionada con cada una de ellas. Cambiar esta selección no cambia la información en la tabla de cuadrícula. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical).
*    En el gráfico **actividad** , el eje Y es el número total de sesiones punto a punto, organizada y de participación en conferencia que se mantienen.
*    En el gráfico actividad de **los usuarios** , el eje Y es el número de usuarios únicos que asisten en cada tipo de punto a punto, organizado y participó en conferencia.

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
En la tabla se muestra un desglose de todas las actividades de conferencia por usuario. Muestra todos los usuarios que tienen Skype empresarial asignado y sus actividades de conferencia. Puede agregar columnas a la tabla.
* **Nombreusuario** es el nombre del usuario.
* **Eliminado** indica que se ha quitado la licencia del usuario.<br/><br/>
  > [!NOTE]
  > La actividad de un usuario eliminado seguirá apareciendo en un informe siempre que tenga una licencia en algún momento durante el período de tiempo seleccionado. La columna **Eliminado** ayuda a ver que el usuario ya no está activo, pero que ha contribuido a los datos del informe.
     
* **Fecha de eliminación** es la fecha en que se quitó la licencia del usuario.
* **Fecha de última actividad (UTC)** es la última vez que el usuario interactuó en una sesión de punto a punto u organizó una conferencia o participó en ella.
* **Punto a punto** muestra el número total de sesiones de conferencia de punto a punto que ha usado el usuario.
* **Conferencias organizadas** muestra el número total de conferencias que ha organizado el usuario.
* **Conferencias participadas** muestra el número total de conferencias en que ha participado el usuario.
* **Producto asignado** hace referencia a los productos de Office 365 asignados a este usuario.<br/>

Si las directivas de su organización le impiden ver informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Ocultar detalles de usuario en la sección informes** de los [informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8](../images/sfbcallout8.png)<br/>
Haga clic o pulse en el icono **columnas** de cualquiera de las columnas para agregar o quitar columnas del informe.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Botón de exportación de informes de Skype empresarial.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe en sí. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de uso de dispositivos de Skype empresarial](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles, que tienen la aplicación Skype empresarial instalada y la usan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype empresarial](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios las conferencias que usan la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones, la web, las llamadas entrantes/salientes y las llamadas entrantes y salientes de Microsoft.
    
- [Informe de actividad punto a punto de Skype empresarial](peer-to-peer-activity-report.md) Puede ver cuánto usan los usuarios mi, audio/vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Informe de usuarios bloqueados de Skype empresarial](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.
    
- [Informe de uso de RTC de Skype empresarial](pstn-usage-report.md) Puede ver la cantidad de minutos invertidos en llamadas entrantes o salientes, así como el coste de estas llamadas.

- [Informe de grupos de minutos RTC de Skype empresarial](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes en curso en la organización.

- [Informe de detalles de sesión de Skype empresarial](session-details-report.md) Puede ver los detalles de las experiencias de llamadas de los usuarios individuales.

    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
