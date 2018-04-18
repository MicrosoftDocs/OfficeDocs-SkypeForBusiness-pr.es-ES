---
title: Informe de uso PSTN
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
description: El nuevo Skype para el área del centro de administración de negocio informes muestra realiza la llamada y audio conferencia actividad en su organización. Permite profundizar en los informes para brindar información más detallada acerca de las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles del uso de PSTN de conferencia de Audio incluyendo el costo de la llamada para que pueda comprender su uso y llame a los detalles de facturación para determinar el uso dentro de la organización.
ms.openlocfilehash: 6ee6606ae37e02d07e3c3e57ca9fee529b150626
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="pstn-usage-report"></a>Informe de uso PSTN

El nuevo Skype para el área de **informes** del centro de administración de negocios muestra realiza la llamada y audio conferencia actividad en su organización. Permite profundizar en los informes para brindar información más detallada acerca de las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles del uso de PSTN de conferencia de Audio incluyendo el costo de la llamada para que pueda comprender su uso y llame a los detalles de facturación para determinar el uso dentro de la organización.
  
Consulte la [información general de informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para informes más que están disponibles.
  
Este informe, junto con lo otro Skype para los informes de negocios, ofrece detalles sobre la actividad incluyendo llamada uso en toda la organización. Estos detalles son muy útiles cuando usted investigando, planear y realizar otros negocios las decisiones para su organización y para la configuración de [comunicaciones créditos](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Podrá ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

- Ir al **Centro de administración de Office 365** > **centra Admin** > **Skype para el centro de administración de negocios** > **informes** > **Detalles de uso de RTC**.
    
    > [!NOTE]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Informe de uso de RTC de Skype Empresarial](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Muestra todos los usuarios con Skype para empresas asignados a ellos y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    **Call ID** es el identificador de llamada para una llamada. Es un identificador único para la llamada que se utiliza al llamar a soporte técnico de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **Número de teléfono** es el Skype para el número de teléfono profesional que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes.
*    **Ubicación de usuario** es el país o región donde se encuentra el usuario.
*    **Identificador** es el número de teléfono del que llama (identificador) para las llamadas entrantes, el número de que originó la llamada o el Skype para número de negocio desde el que se originó la llamada para las llamadas salientes.
*    **Tipo de llamada** es si la llamada fue llamar un PSTN entrante o saliente y coloca el tipo de llamada como una llamada de un usuario o una conferencia de audio. Puede ver los tipos de llamada son: 

     **Tipos de llamada planes de llamada** 
     *    **user_in** (el usuario recibe una llamada entrante de RTC) 
     *    **user_out** (el usuario coloca una llamada saliente de RTC) 
     *    **user_out_conf** (el usuario agregado a 2 o más participantes PSTN a la llamada como una llamada de conferencia de 3 vías) 
     *    **user_out_transfer** (el usuario transfiere la llamada a un número de RTC) 
     *    **user_out_forwarding** (el usuario reenvía la llamada a un número de RTC)

     **Tipos de llamadas de conferencia de audio**
     *    **conf_in** (una llamada entrante en el puente de conferencia de Audio) 
     *    **conf_out** (una llamada saliente que va desde el puente de conferencia de Audio normalmente para agregar un número PSTN a la conferencia)

     **Aplicaciones de comunicaciones unificadas (UCAP)** 
     *    **ucap_in** (una llamada entrante a la aplicación de comunicaciones unificadas como cola de operador o llamada automática) 
     *    **ucap_out** (una llamada saliente de la aplicación de comunicaciones unificadas como cola de operador o llamada automática)
*     
     **Nacionales e internacionales** indica si la llamada que se colocó consideró nacionales (dentro de un país o región) o internacionales (fuera de un país o región) basado en la ubicación del usuario. 
*    **Marcado de destino** es el nombre del destino del país o región que se marca como Francia, Alemania o los Estados Unidos (US). 
*    **Tipo de número** es el tipo de número de teléfono en el número de teléfono de un usuario, un servicio o un número de teléfono gratuito.  
*    **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. 
*    **Duración** muestra el tiempo durante el cual ha estado conectada la llamada.  
*    **ConfID** es el identificador de la conferencia de la conferencia de audio. 
*    **Cargo** es la cantidad de dinero o el coste de la llamada que se cobran a su cuenta. 
*    **Moneda** es el tipo de moneda que se usa para calcular el coste de la llamada. 
*    **La capacidad** es la licencia que se utiliza para la llamada. Puede ver los tipos de licencia son: 
     *    **MCOPSTNPP** - créditos de comunicaciones <br/> **MCOPSTN1** - Plan de llamadas nacionales (3000 min US / min 1200 UE planes) 
     *    **MCOPSTN2** - Plan de llamadas internacionales 
     *    **MCOPSTN5** - domésticos llamando a Plan (plan de llamadas de 120 minutos) 
     *    **MCOMEETADD** - conferencia de Audio
     *    **MCOMEETACPEA** - pago por minuto de audioconferencias 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar el informe de los datos en una ficha delimitado por archivo de Excel, haciendo clic o punteando en el botón **Exportar a Excel** . <br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype para el informe de la actividad de negocio](activity-report.md) Puede ver cuánto los usuarios utilizan peer-to-peer, organizada y participó en sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](device-usage-report.md) Puede ver los dispositivos incluyendo sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype para el negocio de la aplicación instalada y lo utilizan para mensajería instantánea y reuniones.
    
- [Skype para informe de actividad de negocio conferencia multimedia](conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizando las conferencias que utilizan la mensajería instantánea, audio o vídeo, compartir aplicaciones, Web, /dial out - 3ª parte y /dial — Microsoft.
    
- [Skype para informe de actividad de participantes de conferencia de negocio](conference-participant-activity-report.md) Puede ver cuántos de mensajería instantánea, audio y vídeo, uso compartido de aplicaciones, Web y marcado a cabo conferencias de audio están siendo participados en.
    
- [Skype para informe de actividad de igual a igual de negocio](peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype para usuarios de negocios bloqueado informe](users-blocked-report.md) Puede ver los usuarios de su organización que le impide realizar llamadas PSTN.

- [Skype para informe de minuto grupos empresariales PSTN](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes actual dentro de la organización.

- [Skype para el informe de detalles de sesión de negocios](session-details-report.md) Puede ver detalles acerca de experiencias de llamada del usuario individual.
    
## <a name="related-topics"></a>See also
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
