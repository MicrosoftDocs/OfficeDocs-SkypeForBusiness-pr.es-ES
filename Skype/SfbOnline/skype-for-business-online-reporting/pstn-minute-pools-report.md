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
description: El nuevo Skype Empresarial de informes del Centro de administración muestra la actividad de llamadas y audioconferencias en su organización. Le permite explorar en profundidad los informes para proporcionar información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe Skype Empresarial grupos de minutos RTC para ver el número de minutos consumidos durante el mes actual dentro de su organización.
ms.openlocfilehash: d82f360c48b6e7478ef552826ee80ecaf508db0f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238184"
---
# <a name="pstn-minute-pools-report"></a>Informe de grupos de minutos de RTC

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>Este informe solo está disponible para obtener una vista previa de los clientes.

El nuevo área Skype Empresarial informes **del** Centro de administración muestra la actividad de llamadas y audioconferencias en su organización. Le permite explorar en profundidad los informes para proporcionar información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe Skype Empresarial grupos de minutos **RTC** para ver el número de minutos consumidos durante el mes actual dentro de su organización.
  
Consulte información general [sobre informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes disponibles.
  
Este informe, junto con el resto de Skype Empresarial, le proporciona detalles sobre la actividad en toda la organización. Estos detalles son muy útiles al investigar, planear y tomar otras decisiones empresariales para su organización y para configurar créditos [de comunicaciones](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes Skype Empresarial al iniciar sesión como administrador en el centro de Microsoft 365 administración. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Cómo obtener acceso al informe de Skype Empresarial de minutos RTC

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

- Vaya al centro de administración > **centros de administración** Skype Empresarial grupos de minutos RTC informes del centro de  >    >    >  **administración.**
    
> [!NOTE]
> Dependiendo de Microsoft 365 o Office 365 suscripción que tenga, es posible que no vea todos los mismos detalles que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar el informe Skype Empresarial grupos de minutos RTC

Puede obtener una vista en los grupos de Skype Empresarial minutos del usuario consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
## 

![Skype Empresarial Informe de grupos de minutos RTC](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de los grupos de minutos por licencia (capacidad) y ubicación de uso. 
*    **La funcionalidad** es el plan de licencia o servicio que se usa para la llamada. Los planes de licencia o servicio que puede ver en este informe incluyen:
     * MCOPSTN1: Plan de llamadas nacionales (planes de 3000 minutos para EE. UU. y 1200 minutos para la UE
     * MCOPSTN2: Plan de llamadas internacionales de & nacionales desde el que verá una piscina nacional (3000 minutos EE.UU./Canadá/PR, países europeos de 1200 minutos) y una piscina internacional (600 minutos). El límite de minutos se alcanza siempre que se alcance el límite nacional -O- internacional dentro del mes calendario. 
     * MCOPSTN5 - Plan de llamadas nacionales (plan de llamadas de 120 minutos)
     * MCOPSTN6 : Plan de llamadas nacionales (plan de llamadas de 240 minutos)
     * MCOMEETADD- Audioconferencia
*    **Descripción de capacidad** es una descripción del tipo de licencia utilizado para la llamada.
*    **Grupo de minutos de** país es la ubicación de uso de licencia de los usuarios que comparten el grupo de minutos. 
*    **Minutos usados** es el número de minutos usados cada mes.
*    **Total Minutos** es el número total de minutos disponibles para el mes. 
*    **Porcentaje usado** es el porcentaje de minutos usados para el mes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype Empresarial actividad](activity-report.md) Puede ver cuánto usan los usuarios de punto a punto, organizados y participados en sesiones de conferencia.
    
- [Skype Empresarial de uso de dispositivos](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación Skype Empresarial instalada y la usan para mensajería instantánea y reuniones.
    
- [Skype Empresarial actividad del organizador de conferencias](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios conferencias que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, Web, /dial out - terceros y /dial out - Microsoft.
    
- [Skype Empresarial actividad de los participantes de la conferencia](conference-participant-activity-report.md) Puede ver cuántas conferencias de audio, audio y vídeo, uso compartido de aplicaciones, Web y llamadas de audio se están participando en.
    
- [Skype Empresarial de actividad punto a punto](peer-to-peer-activity-report.md) Puede ver la cantidad de usuarios que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype Empresarial de usuarios bloqueados](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.

- [Skype Empresarial detalles de la sesión](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el Centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
