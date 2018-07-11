---
title: Informe de uso de RTC
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: El nuevo Skype para el área de informes del centro de administración empresarial muestra realiza la llamada y audio conferencia actividad en la organización. Permite profundizar en los informes para proporciona una idea más granular acerca de las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver detalles de uso de RTC de conferencia de Audio incluido el costo de la llamada para que pueda comprender su uso y llamar a los detalles de facturación para determinar el uso dentro de la organización.
search.appverid: MET150
ms.openlocfilehash: 3c2148b54c04950867feef1844a4ca1595f708e5
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246492"
---
# <a name="pstn-usage-report"></a>Informe de uso de RTC

El nuevo Skype para el área de **informes** del centro de administración empresarial muestra realiza la llamada y audio conferencia actividad en la organización. Permite profundizar en los informes para proporciona una idea más granular acerca de las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver detalles de uso de RTC de conferencia de Audio incluido el costo de la llamada para que pueda comprender su uso y llamar a los detalles de facturación para determinar el uso dentro de la organización.
  
Revise la [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes que están disponibles.
  
Este informe, junto con los otro Skype para los informes de negocio, proporciona detalles sobre la actividad incluyendo llamar al uso en toda la organización. Estos detalles son muy útiles cuando se investigar, planear y realizar otros profesionales las decisiones durante la para su organización y para la configuración de [comunicaciones créditos](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Podrá ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

- Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para el centro de administración de negocio** > **informes** > **Detalles de uso de RTC**.
    
    > [!NOTE]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Informe de uso de RTC de Skype Empresarial](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Muestra todos los usuarios que tienen Skype para la empresa asignada a ellas y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    **Identificador de llamada** es el identificador de llamada para una llamada. Es un identificador único para la llamada que se usa al llamar a soporte técnico de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **Número de teléfono** es el Skype para el número de teléfono profesional que recibió la llamada para llamadas entrantes o el número marcado para las llamadas salientes.
*    **Ubicación de usuario** es el país o región donde se encuentra el usuario.
*    **Identificador de autor de la llamada** es el número de teléfono del autor de la llamada (identificador de autor de la llamada) para las llamadas entrantes, el número de que se ha originado la llamada o el Skype para el número de trabajo desde la que se originó la llamada para las llamadas salientes.
*    **Tipo de llamada** es si la llamada tuvo una RTC entrante o saliente de llamadas y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamada, es posible que vea son: 

     **Tipos de llamada del Plan de llamada** 
     *    **user_in** (el usuario recibe una llamada entrante de RTC) 
     *    **user_out** (el usuario realiza una llamada saliente de RTC) 
     *    **user_out_conf** (el usuario agregado a 2 o más participantes de RTC a la llamada como una llamada de conferencia de canales de 3) 
     *    **user_out_transfer** (el usuario transfiere la llamada a un número de RTC) 
     *    **user_out_forwarding** (el usuario reenviar la llamada a un número de RTC)

     **Tipos de llamada de conferencia de audio**
     *    **conf_in** (es decir, una llamada entrante para el puente de conferencia de Audio) 
     *    **conf_out** (una llamada saliente que va desde el puente de conferencia de Audio normalmente para agregar un número RTC a la conferencia)

     **Aplicaciones de comunicaciones unificadas (UCAP)** 
     *    **ucap_in** (una llamada de RTC entrante a la aplicación de comunicaciones unificadas como una cola de llamada o de operador automático) 
     *    **ucap_out** (una llamada de RTC saliente desde la aplicación de comunicaciones unificadas como cola de llamada o de operador automático)
     *    **Nota:** Las llamadas que se han transferido a un usuario de la aplicación de comunicaciones unificadas, como una cola de llamada o de operador automático no aparecerán en el informe de uso de RTC como estos tramos de llamada son las llamadas de audio de punto a punto (P2P). Puede obtener acceso a las llamadas de P2P en la Skype para el centro de administración de negocio en "Herramientas > Skype para Business llamar Analytics" y buscar por dirección SIP o el nombre de usuario que correlaciona la llamada por fecha y hora o que se originan CLID (identificador de la línea de llamada). 
*     
     **Nacional o internacional** le indica si la llamada que se ha colocado se consideró nacionales (dentro de un país o región) o internacionales (fuera de un país o región) según la ubicación del usuario. 
*    **Marcado de destino** es el nombre del destino del país o región que se marca como Francia, Alemania o de los Estados Unidos (US). 
*    **Tipo de número** es el tipo de número de teléfono que va desde el número de teléfono de un usuario, un servicio o el número de teléfono gratuito.  
*    **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. 
*    **Duración** muestra el tiempo durante el cual ha estado conectada la llamada.  
*    **ConfID** es el identificador de la conferencia de la conferencia de audio. 
*    **Cargo** es la cantidad de dinero o costo de la llamada que se carga a su cuenta. 
*    **Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. 
*    **Se trata de la licencia que se usa para la llamada.** Los tipos de licencia que es posible que vea son: 
     *    **MCOPSTNPP** - Communications créditos <br/> **MCOPSTN1** - llamar a planear nacionales (3000 min US / planes de 1200 min la Unión Europea) 
     *    **MCOPSTN2** - Plan de llamadas internacionales 
     *    **MCOPSTN5** - nacionales llamar a Plan (plan llamada 120 minutos) 
     *    **MCOPSTN6** - nacionales llamar a Plan (plan de llamadas de 240 min) Nota: disponibilidad limitada
     *    **MCOMEETADD** - conferencias de Audio
     *    **MCOMEETACPEA** - pago por minuto conferencias de Audio 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar el informe de datos en una ficha delimitada por el archivo de Excel, haciendo clic o punteando en el botón **Exportar a Excel** . <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para informe de actividad de negocio](activity-report.md) Puede ver la cantidad de los usuarios están usando peer-to-peer, organizada y participó en las sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede para ver los dispositivos incluidos los sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype para la aplicación empresarial de instalan y están usando para la mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de organizador de conferencia empresarial](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizar conferencias que utilizan la mensajería instantánea, audio y vídeo, compartir aplicaciones, Web, /dial out - 3rd fabricantes y /dial out - Microsoft.
    
- [Skype para informe de actividad de participantes de conferencia empresarial](conference-participant-activity-report.md) Puede ver cuántos de mensajería instantánea, audio y vídeo, uso compartido de aplicaciones, Web y acceso telefónico a conferencias de audio que se están participó en.
    
- [Skype para informe de actividad de punto a punto de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Informe de bloqueados de Skype para usuarios profesionales](users-blocked-report.md) Puede ver los usuarios de la organización que se han bloqueado desde la realización de llamadas de RTC.

- [Skype para informe de grupos de servidores minuto RTC de negocio](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.

- [Skype para el informe de detalles de sesiones de negocio](session-details-report.md) Puede ver detalles acerca de las experiencias de llamada de usuario individual.
    
## <a name="related-topics"></a>See also
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
