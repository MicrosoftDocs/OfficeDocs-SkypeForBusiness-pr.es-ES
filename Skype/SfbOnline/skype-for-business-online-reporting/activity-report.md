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
ms.openlocfilehash: f50b8c03304a308594fd7bd920ee92e8d38a1f43
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205561"
---
# <a name="activity-report"></a>Informe de actividad

El **panel** Informes muestra la información general de la actividad de los productos de Microsoft 365 u Office 365 de su organización. Le permite explorar informes individuales de nivel de producto para darle más información pormenorizados acerca de las actividades dentro de cada producto. Por ejemplo, puede usar el informe de actividad de **Skype** Empresarial para ver cuánto utilizan sus usuarios las sesiones de conferencia punto a punto u organizadas, o cuánto participan en las sesiones de conferencia. 

Consulte la información [general de los informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más información.
  
Este informe, junto con los demás informes de Skype Empresarial, le ofrece detalles sobre la actividad en toda su organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización.
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Cómo acceder al informe de actividad de Skype Empresarial

1. Vaya al Centro de administración para > **uso de**  >  **informes.**
    
2. En la **página** Uso, elija **Actividad** de Skype Empresarial en la lista Seleccionar un informe de la izquierda o haga clic en el widget actividad  >   de  **Skype** Empresarial.

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar el informe de actividad de Skype Empresarial

Puede obtener una vista de la actividad de Skype Empresarial de su usuario consultando los gráficos **Actividad** y **Usuarios**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
Puede **visualizar el**  informe de actividad de correo electrónico de actividad de Skype Empresarial para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si hace clic en un día concreto en el informe, la tabla (ver el número 7) mostrará los datos de hasta 28 días desde la fecha actual (no la fecha en la que se generó el informe).

> [!NOTE]
> Si hace clic en los detalles de un día específico, la tabla solo mostrará los datos de los 30 días hasta la fecha en la que se generó el informe.

***
![Número 2](../images/sfbcallout2.png)<br/>
Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 a 48 horas desde el momento de actividad. 
***
![Número 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número de actividades de conferencia que se están llevando a cabo en su organización. Le mostrará el número total y los tipos de sesiones **Punto a punto**, **Organizadas** y **Participadas** en las sesiones de conferencia de toda su organización.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Utilice los datos del gráfico interactivo **Usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades de conferencia realizadas en su organización. Se muestra el número total de usuarios y los tipos de sesiones punto a punto **,** organizadas y participadas en **sesiones** de conferencia.
***
![Número 5](../images/sfbcallout5.png)<br/>
Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo,  en el gráfico de actividades, haga clic o  pulse sesiones de punto a punto **,** organizadas o participadas para ver solo la información relacionada con cada una de ellas.  Cambiar esta selección no cambia la información en la tabla de cuadrícula. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical).
*    En el **gráfico de** actividad, el eje Y es el número total de sesiones punto a punto, organizadas y participadas en las conferencias que se han realizado.
*    En el **gráfico de** actividad Usuarios, el eje Y es el número de usuarios únicos que asisten a cada tipo de conferencia punto a punto, organizada y participada.

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
La tabla muestra un desglose de todas las actividades de conferencia por usuario. Se muestran todos los usuarios que tienen Skype Empresarial asignado y sus actividades de conferencia. Puede agregar columnas a la tabla.
* **Nombre** de usuario es el nombre del usuario.
* **Eliminado** indica que se ha quitado la licencia del usuario.<br/><br/>
  > [!NOTE]
  > La actividad de un usuario eliminado se seguirá visualizando en un informe siempre que la licencia se haya concedido en algún momento durante el período de tiempo seleccionado. La columna **Eliminado** ayuda a ver que el usuario ya no está activo, pero que ha contribuido a los datos del informe.
     
* **Fecha de eliminación** es la fecha en que se quitó la licencia del usuario.
* **Fecha de última actividad (UTC)** es la última vez que el usuario interactuó en una sesión de punto a punto u organizó una conferencia o participó en ella.
* **Punto a punto muestra** el número total de sesiones de conferencia de punto a punto que ha utilizado el usuario.
* **Conferencias organizadas** muestra el número total de conferencias que ha organizado el usuario.
* **Conferencias participadas** muestra el número total de conferencias en que ha participado el usuario.
* **El producto** asignado es los productos de Microsoft 365 u Office 365 asignados a este usuario.<br/>

Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la opción **Ocultar detalles de usuario en la sección Informes** de informes del Centro de [administración.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
***
![Número 8](../images/sfbcallout8.png)<br/>
Haga clic o pulse **en el icono** Columnas de cualquiera de las columnas para agregar o quitar columnas del informe.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Botón Exportar de informes de Skype Empresarial.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de uso de dispositivos de Skype Empresarial](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles, que tienen la aplicación de Skype Empresarial instalada y la están usando para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype Empresarial](conference-organizer-activity-report.md) Puede ver cuánto utilizan sus usuarios las conferencias que utilizan la MI, el audio/vídeo, el uso compartido de aplicaciones, la Web, las llamadas de terceros y las llamadas locales y las llamadas a través de terceros (Microsoft).
    
- [Informe de actividad punto a punto de Skype Empresarial](peer-to-peer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de usuarios bloqueados de Skype Empresarial](users-blocked-report.md) Puede ver los usuarios de su organización a los que se les ha bloqueado la realización de llamadas RTC.
    
- [Informe de uso de RTC de Skype Empresarial](pstn-usage-report.md) Puede ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas.

- [El informe de los grupos de](pstn-minute-pools-report.md) minutos RTC de Skype Empresarial permite ver el número de minutos consumidos durante el mes actual dentro de su organización.

- [Informe de detalles de la sesión de Skype Empresarial](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.

    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
