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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: El nuevo Skype para el área de informes del centro de administración empresarial muestra realiza la llamada y audio conferencia actividad en la organización. Permite profundizar en los informes para proporciona una idea más granular acerca de las actividades de cada usuario. Por ejemplo, puede usar el Skype para informe de grupos de servidores minuto RTC de negocio para ver el número de minutos consumidos durante el mes actual dentro de la organización.
ms.openlocfilehash: 2840ac4bde1234f0f87fe17c41f43b6efad647b5
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182379"
---
# <a name="pstn-minute-pools-report"></a>Informe de grupos de minutos de RTC

>[!NOTE]
>Este informe solo está disponible para obtener una vista previa de los clientes.

El nuevo Skype para el área de **informes** del centro de administración empresarial muestra realiza la llamada y audio conferencia actividad en la organización. Permite profundizar en los informes para proporciona una idea más granular acerca de las actividades de cada usuario. Por ejemplo, puede usar el informe de **Skype para grupos de negocio RTC minutos** para ver el número de minutos consumidos durante el mes actual dentro de la organización.
  
Revise la [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes que están disponibles.
  
Este informe, junto con los otro Skype para los informes de negocio, proporciona detalles sobre la actividad en toda la organización. Estos detalles son muy útiles al investigar, planear y realizar otras decisiones empresariales para su organización y para la configuración de [Comunicaciones de créditos](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Podrá ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Cómo llegar a la Skype para informe de grupos de servidores minuto RTC de negocio

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

- Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para el centro de administración de negocio** > **informes** > **grupos minutos de RTC**.
    
> [!NOTE]
> Dependiendo de la suscripción a Office 365 que tiene, es posible que no verá todos los mismos detalles que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar el Skype para informe de grupos de servidores minuto RTC de negocio

Puede obtener una vista en Skype del usuario para los grupos de negocio minutos mirando en cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
## 

![Informe de grupos de servidores de Skype para minuto de RTC de negocio](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de los grupos de servidores minutos por licencia (capacidad) y la ubicación de uso. 
*    **Capacidad** es el plan de licencia/servicio utilizado para la llamada. Los planes de licencia o servicio que puede ver en este informe se incluyen:
     * MCOPSTN1 - nacionales llamar a planear (3000 minuto 1200/US-minuto UE planes
     * MCOPSTN2 - nacionales & internacional llamar a planear desde la que podrá ver un grupo de servidores interno (3000 minuto Estados Unidos, Canadá/PR, 1200 minuto países de Europa) y un grupo de servidores internacional (600 minutos). Minuto cap se alcanza cada vez que se alcanza el cap OR internacional nacional dentro del mes del calendario. 
     * MCOPSTN5 - nacionales llamar a Plan (plan llamada 120 minutos)
     * MCOPSTN6 - nacionales llamar a Plan (plan de llamadas de 240 minutos)
     * MCOMEETADD - conferencias de Audio
*    **Descripción de la capacidad** es una descripción del tipo de licencia utilizado para la llamada.
*    **Grupo de servidores de minuto de país** es la ubicación de uso de licencia de los usuarios que comparten el grupo de minuto. 
*    **Usa minutos** es el número de minutos que se usa cada mes.
*    **Total de minutos** es el número total de minutos disponibles para el mes. 
*    **Porcentaje utilizado** es el porcentaje de minutos utilizados para el mes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. 
***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**. <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 a los usuarios, puede ordenar y filtrar dentro de la tabla en el informe de sí mismo. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para informe de actividad de negocio](activity-report.md) Puede ver la cantidad de los usuarios están usando peer-to-peer, organizada y participó en las sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede para ver los dispositivos incluidos los sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype para la aplicación empresarial de instalan y están usando para la mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de organizador de conferencia empresarial](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizar conferencias que utilizan la mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, /dial out - 3rd fabricantes y /dial out - Microsoft.
    
- [Skype para informe de actividad de participantes de conferencia empresarial](conference-participant-activity-report.md) Puede ver cuántos de mensajería instantánea, audio y vídeo, uso compartido de aplicaciones, Web y acceso telefónico a conferencias de audio que se están participó en.
    
- [Skype para informe de actividad de punto a punto de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Informe de bloqueados de Skype para usuarios profesionales](users-blocked-report.md) Puede ver los usuarios de la organización que se han bloqueado desde la realización de llamadas de RTC.

- [Skype para el informe de detalles de sesiones de negocio](session-details-report.md) Puede ver detalles acerca de las experiencias de llamada de usuario individual.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
