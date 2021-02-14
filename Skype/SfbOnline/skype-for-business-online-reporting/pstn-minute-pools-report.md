---
title: Informe de grupos de minutos de RTC
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
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
description: El nuevo área informes del Centro de administración de Skype Empresarial muestra la actividad de llamadas y audioconferencias de su organización. Le permite explorar en profundidad los informes para darle una visión más granular de las actividades de cada usuario. Por ejemplo, puede usar el informe de grupos de minutos RTC de Skype Empresarial para ver el número de minutos consumidos durante el mes actual dentro de su organización.
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776255"
---
# <a name="pstn-minute-pools-report"></a>Informe de grupos de minutos de RTC

>[!NOTE]
>Este informe solo está disponible para los clientes de la versión preliminar.

El nuevo área informes del Centro de administración **de** Skype Empresarial muestra la actividad de llamadas y audioconferencias de su organización. Le permite explorar en profundidad los informes para darle una visión más granular de las actividades de cada usuario. Por ejemplo, puede usar el informe de grupos de minutos RTC de **Skype** Empresarial para ver el número de minutos consumidos durante el mes actual dentro de su organización.
  
Consulte la información [general de los informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver más informes que están disponibles.
  
Este informe, junto con los demás informes de Skype Empresarial, le ofrece detalles sobre la actividad en toda su organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización, así como para configurar créditos [de comunicaciones.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Cómo obtener el informe de grupos de minutos RTC de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

- Vaya al Centro de administración > centro de **administración de** Skype Empresarial Para informes de grupos de  >    >    >  **minutos RTC.**
    
> [!NOTE]
> Según la suscripción a Microsoft 365 u Office 365 que tenga, es posible que no vea los mismos detalles que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar el informe de grupos de minutos RTC de Skype Empresarial

Puede obtener una vista de los grupos de minutos de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
## 

![Informe de grupos de minutos RTC de Skype Empresarial](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de los grupos de minutos por licencia (funcionalidad) y ubicación de uso. 
*    **La funcionalidad** es el plan de licencia/servicio usado para la llamada. Los planes de licencia o servicio que puede ver en este informe incluyen:
     * MCOPSTN1- Plan de llamadas nacionales (planes de la UE de 3000 minutos para EE. UU. y 1200 minutos
     * MCOPSTN2: plan de llamadas internacionales & nacionales desde el que verá una fondo de servidores nacional (3000 minutos para Estados Unidos,Canadá/PR, países europeos de 1200 minutos) y una fondo internacional (600 minutos). El límite de minutos se alcanza siempre que se alcanza el límite nacional -O- internacional dentro del mes natural. 
     * MCOPSTN5- Plan de llamadas nacionales (plan de llamadas de 120 minutos)
     * MCOPSTN6- Plan de llamadas nacionales (plan de llamadas de 240 minutos)
     * MCOMEETADD - Audioconferencia
*    **Capability Description** es una descripción del tipo de licencia usado para la llamada.
*    **Grupo de minutos del** país es la ubicación de uso de licencia de los usuarios que comparten el grupo de minutos. 
*    **Minutos usados** es el número de minutos utilizados cada mes.
*    **Minutos totales** es el número total de minutos disponibles para el mes. 
*    **El porcentaje usado** es el porcentaje de minutos utilizados para el mes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de actividad de Skype Empresarial](activity-report.md) Puede ver cuánto utilizan sus usuarios las sesiones de conferencia punto a punto, organizadas y participadas.
    
- [Informe de uso de dispositivos de Skype Empresarial](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación de Skype Empresarial instalada y que lo utilizan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype Empresarial](conference-organizer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones, la Web, /dial out - terceros y /dial out - Microsoft.
    
- [Informe de actividad de participantes de conferencias de Skype Empresarial](conference-participant-activity-report.md) Puede ver en cuántas conferencias de audio de mi, audio/vídeo, uso compartido de aplicaciones, web y de llamada están participando.
    
- [Informe de actividad punto a punto de Skype Empresarial](peer-to-peer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de usuarios bloqueados de Skype Empresarial](users-blocked-report.md) Puede ver los usuarios de su organización a los que se les ha bloqueado la realización de llamadas RTC.

- [Informe de detalles de la sesión de Skype Empresarial](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
