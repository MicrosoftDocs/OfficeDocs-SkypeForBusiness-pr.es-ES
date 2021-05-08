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
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 094d947088b1a1fea4a8585e09bdedfa6ffe2a2b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238316"
---
# <a name="activity-report"></a>Informe de actividad

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En **el panel** Informes se muestra la información general sobre la actividad en Microsoft 365 o Office 365 productos de su organización. Le permite profundizar en informes individuales de nivel de producto para proporcionar información más detallada sobre las actividades dentro de cada producto. Por ejemplo, puede usar el informe de actividad de Skype Empresarial para ver cuánto usan los usuarios sesiones de conferencia de punto **a** punto u organizadas, o cuánto están participando en las sesiones de conferencia. 

Consulte información general [sobre informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más información.
  
Este informe, junto con el resto de Skype Empresarial, le proporciona detalles sobre la actividad en toda la organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización.
  
> [!NOTE]
> Puede ver todos los informes Skype Empresarial al iniciar sesión como administrador en el centro de Microsoft 365 administración. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Cómo acceder al informe de actividad de Skype Empresarial

1. Vaya al Centro de administración > **Informes**  >  **de uso.**
    
2. En la **página Uso,** elija **Skype Empresarial** actividad en la lista Seleccionar un informe a la izquierda o haga clic en el widget  >   Skype Empresarial **actividad.** 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar el informe de actividad de Skype Empresarial

Puede obtener una vista de la actividad de Skype Empresarial de su usuario consultando los gráficos **Actividad** y **Usuarios**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
El **Skype Empresarial actividad** de correo electrónico de actividad se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un día determinado en el informe, la tabla (vea el número 7) mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

> [!NOTE]
> Si hace clic en los detalles de un día específico, la tabla solo mostrará los datos de los 30 días hasta la fecha en que se generó el informe.

***
![Número 2](../images/sfbcallout2.png)<br/>
Cada informe tiene la fecha del momento en que se generó. Los informes normalmente reflejan una latencia de 24 a 48 horas desde el momento de la actividad. 
***
![Número 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número de actividades de conferencia que se están llevando a cabo en su organización. Le mostrará el número total y los tipos de sesiones **Punto a punto**, **Organizadas** y **Participadas** en las sesiones de conferencia de toda su organización.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Utilice los datos del gráfico interactivo **Usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades de conferencia realizadas en su organización. Le mostrará el número total de usuarios junto con los tipos de sesiones punto **a** punto , **Organizado** y **Participado** en sesiones de conferencia.
***
![Número 5](../images/sfbcallout5.png)<br/>
Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo,  en el gráfico Actividad, haga clic o pulse sesiones punto a punto **,** Organizado o **Participado** para ver solo la información relacionada con cada una de ellas. Cambiar esta selección no cambia la información en la tabla de cuadrícula. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical).
*    En el **gráfico Actividad,** el eje Y es el número total de sesiones de punto a punto, organizadas y participadas en las sesiones de conferencia que se celebren.
*    En el **gráfico de** actividades Usuarios, el eje Y es el número de usuarios únicos que asisten en cada tipo de conferencia de punto a punto, organizados y participantes.

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
La tabla muestra un desglose de todas las actividades de conferencia por usuario. Esto muestra todos los usuarios que tienen Skype Empresarial asignados a ellos y sus actividades de conferencia. Puede agregar columnas a la tabla.
* **Nombre** de usuario es el nombre del usuario.
* **Eliminado** indica que se ha quitado la licencia del usuario.<br/><br/>
  > [!NOTE]
  > La actividad de un usuario eliminado aún se mostrará en un informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. La columna **Eliminado** ayuda a ver que el usuario ya no está activo, pero que ha contribuido a los datos del informe.
     
* **Fecha de eliminación** es la fecha en que se quitó la licencia del usuario.
* **Fecha de última actividad (UTC)** es la última vez que el usuario interactuó en una sesión de punto a punto u organizó una conferencia o participó en ella.
* **Punto a punto** muestra el número total de sesiones de conferencia punto a punto que usó el usuario.
* **Conferencias organizadas** muestra el número total de conferencias que ha organizado el usuario.
* **Conferencias participadas** muestra el número total de conferencias en que ha participado el usuario.
* **Producto asignado** es el Microsoft 365 o Office 365 que se asignan a este usuario.<br/>

Si las directivas de su organización le impiden ver informes en los que la información de usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Ocultar detalles de usuario en la sección Informes** de actividades del Centro de [administración.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
***
![Número 8](../images/sfbcallout8.png)<br/>
Haga clic o pulse en **el icono** Columnas de cualquiera de las columnas para agregar o quitar columnas del informe.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Skype Empresarial Botón Exportar informes.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype Empresarial de uso de dispositivos](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles, que tienen la aplicación Skype Empresarial instalada y la usan para mensajería instantánea y reuniones.
    
- [Skype Empresarial actividad del organizador de conferencias](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios conferencias que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, Web, acceso telefónico/salida - terceros y acceso telefónico local / salida - Microsoft.
    
- [Skype Empresarial de actividad punto a punto](peer-to-peer-activity-report.md) Puede ver cuánto usan los usuarios mi, audio/vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype Empresarial de usuarios bloqueados](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.
    
- [Skype Empresarial de uso de RTC](pstn-usage-report.md) Puede ver el número de minutos invertidos en llamadas entrantes y salientes y el costo de estas llamadas.

- [Skype Empresarial de grupos de minutos](pstn-minute-pools-report.md) RTC puede ver el número de minutos consumidos durante el mes actual dentro de su organización.

- [Skype Empresarial detalles de la sesión](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.

    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el Centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
