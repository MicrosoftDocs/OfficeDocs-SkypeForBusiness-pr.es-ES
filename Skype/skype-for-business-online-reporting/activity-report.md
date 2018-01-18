---
title: Informe de actividad
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: O365E_ReportsS4BActivity
ms.custom: Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: be0cba752c5d516a65ee8533750add2e46345455
ms.sourcegitcommit: 5ef156b78eb64a4370ad8e73b16e1ab5fd8fc976
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2018
---
# <a name="activity-report"></a>Informe de actividad

El nuevo panel de mandos de Office 365 **informes** muestra el resumen de la actividad a través de los productos de Office 365 en su organización. Permite profundizar para informes individuales a nivel de producto para brindar información más detallada acerca de las actividades dentro de cada producto. Por ejemplo, puede utilizar el informe de **Skype para la actividad de negocio** para ver cuánto los usuarios utilizan a peer-to-peer u organizado sesiones de conferencias o cuánto está participando en sesiones de conferencia. 

Consulte la [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más información.
  
Este informe, junto con lo otro Skype para informes empresariales, proporciona detalles sobre la actividad en toda la organización. Estos detalles son muy útiles cuando se están investigando, planificación y otras decisiones de negocio para su organización.
  
> [!NOTE]
> Puede ver todos lo Skype para informes empresariales al iniciar la sesión como administrador en el centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Cómo acceder al informe de actividad de Skype Empresarial

1. Ir al **Centro de administración de Office 365** > **informes** > **uso**.
    
2. En la página de **uso** , haga clic en **Skype para la actividad de negocio** en **Seleccione un informe de lista** de la izquierda, o haga clic en el widget de **Skype para la actividad de negocio** .
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Dependiendo de la suscripción a Office 365 que tiene, puede que no vea todos los productos y los informes que se muestra a continuación. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar el informe de actividad de Skype Empresarial

Puede obtener una vista de la actividad de Skype Empresarial de su usuario consultando los gráficos **Actividad** y **Usuarios**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
El informe de **actividad de Skype Empresarial** se puede usar para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Número 2](../images/sfbcallout2.png)<br/>
Cada informe tiene una fecha para cuando se generó este informe. Los informes suelen reflejan una latencia de 24 a 48 horas de tiempo de actividad. 
***
![Número 3](../images/sfbcallout3.png)<br/>Utilice los datos del gráfico interactivo **Actividad** para comprender las tendencias de uso y ver el número de actividades de conferencia que se están llevando a cabo en su organización. Le mostrará el número total y los tipos de sesiones **Punto a punto**, **Organizadas** y **Participadas** en las sesiones de conferencia de toda su organización.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Utilice los datos de gráfico interactivo en el gráfico de **los usuarios** para comprender las tendencias de uso y ver el número de usuarios únicos que participan en las actividades de la conferencia que se mantienen en la organización. Se mostrará el número total de usuarios junto con los tipos de **sesiones de igual a igual**, **organizado**y **. participación** en sesiones de la conferencia.
***
![Número 5](../images/sfbcallout5.png)<br/>
Puede filtrar la serie que se verá en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el diagrama de **actividad** , haga clic o puntee en **sesiones de igual a igual**, **organizado**o **participadas** para ver sólo la información relacionada con cada uno de ellos. Cambiar esta selección, no cambia la información en la tabla de la cuadrícula. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tiene un eje X (horizontal) y un eje Y (vertical).
*    En el diagrama de **actividad** , el eje Y es el número total de peer-to-peer, organizado y participado en sesiones de conferencias que se llevan a cabo.
*    En el diagrama de actividad de **los usuarios** , el eje Y es el número de usuarios únicos que asisten a cada tipo de peer-to-peer, organizado y participado en la conferencia.

En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
La tabla muestra un desglose de todas las actividades de conferencia por usuario. Muestra todos los usuarios con Skype para empresas asignadas a ellos y sus actividades de conferencia. Puede agregar columnas adicionales a la tabla.
*    **Nombre de usuario** es el nombre del usuario.
*    **Eliminado** indica que se ha quitado la licencia del usuario. <br/> <br/> **Nota:** Actividad para un usuario eliminado seguirá mostrándose en un informe, siempre y cuando él o ella obtuvo la licencia en algún momento durante el período de tiempo seleccionado. La columna **Deleted** le ayuda a tener en cuenta que el usuario ya no esté activo, pero ha contribuido a los datos en el informe.<br/><br/>
*    **Deleted fecha** es la fecha en la que se ha quitado la licencia del usuario.
*    **Fecha de última actividad (UTC)** es la última vez que el usuario interactuó en una sesión de punto a punto u organizó una conferencia o participó en ella.
*    **Igual a** muestra el número total de sesiones de la conferencia de peer-to-peer que utiliza el usuario.
*    **Conferencias organizadas** muestra el número total de conferencias que ha organizado el usuario.
*    **Conferencias participadas** muestra el número total de conferencias en que ha participado el usuario.
*    **Producto asignado** hace referencia a los productos de Office 365 asignados a este usuario.<br/>

Si las directivas de su organización le impiden ver informes donde la información de usuario es identificable, puede cambiar la configuración de privacidad para todos estos informes. Consulte la sección **Ocultar detalles de usuario en los informes** en los [Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8](../images/sfbcallout8.png)<br/>
Haga clic o puntee en el icono de **columnas** en alguna de las columnas para agregar o quitar columnas del informe.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o pulsando o tocando en **Exportar**.           <br/> ![Botón de exportación de Skype para Reporting de negocios.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Esto exporta los datos de todos los usuarios y permite realizar la ordenación y el filtrado para un posterior análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe. Si tiene más de 2000 usuarios, con el fin de filtrar y ordenar, debe exportar los datos. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y dispositivos móviles, que tienen el Skype para el negocio de la aplicación instalada y lo utilizan para mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de negocio conferencia multimedia](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizando las conferencias que utilizan mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, dial-in/out - 3ª parte y el dial-in/out - Microsoft.
    
- [Skype para informe de actividad de igual a igual de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan aplicaciones de audio y vídeo, mensajería instantánea, compartir y transferir archivos.
    
- [Skype para usuarios de negocios bloqueado informe](users-blocked-report.md) Puede ver los usuarios de su organización que le impide realizar llamadas PSTN.
    
- [Skype para el informe de uso del negocio PSTN](pstn-usage-report.md) Puede ver el número de minutos dedicado a llamadas de entrada y de salida y el costo para estas llamadas.

- [Skype para informe de minuto grupos empresariales PSTN](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.

- [Skype para el informe de detalles de sesión de negocios](session-details-report.md) Puede ver detalles acerca de experiencias de llamada del usuario individual.

    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

