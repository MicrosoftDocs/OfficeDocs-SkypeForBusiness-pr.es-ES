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
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: El nuevo área informes del centro de administración de Skype empresarial muestra la actividad de llamadas y audioconferencias en su organización. Le permite profundizar en los informes para proporcionarle información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de conferencias de audio, incluido el costo de la llamada, para que pueda comprender su uso y los detalles de facturación para determinar el uso dentro de su organización.
ms.openlocfilehash: 3d5ea4552cec8e9f10ad0108dad4c00875918c0e
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35587920"
---
# <a name="pstn-usage-report"></a>Informe de uso de RTC

El nuevo área **informes** del centro de administración de Skype empresarial muestra la actividad de llamadas y audioconferencias en su organización. Le permite profundizar en los informes para proporcionarle información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de conferencias de audio, incluido el costo de la llamada, para que pueda comprender su uso y los detalles de facturación para determinar el uso dentro de su organización.
  
Consulte la [información general](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) de los informes para ver más informes que están disponibles.
  
Este informe, junto con los otros informes de Skype empresarial, ofrece detalles sobre la actividad, lo que incluye el uso en toda la organización. Estos detalles son muy útiles para investigar, planear y tomar otras decisiones empresariales para su organización y para configurar [créditos de comunicaciones](/microsoftteams/what-are-communications-credits) .
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

- Vaya al centro de administración de **Office 365** > **** > el centro > de administración centro**de administración de Skype empresarial****informa** > de los**detalles de uso de RTC**.
    
    > [!NOTE]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Informe de uso de RTC de Skype Empresarial](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Se muestran todos los usuarios que tienen Skype empresarial asignado y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    El **identificador de llamada** es el identificador de llamada de una llamada. Es un identificador único para la llamada que se usa al llamar a soporte técnico de servicios de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **Número de teléfono** es el número de teléfono de Skype para empresas que recibió la llamada para llamadas entrantes o el número marcado para llamadas salientes.
*    **Ubicación del usuario** es el país o la región donde se encuentra el usuario.
*    La **identificación de llamadas** es el número de teléfono de la persona que llama (identificador de la llamada) para las llamadas entrantes, el número desde el que se originó la llamada o el número de Skype empresarial desde el que se originó la llamada para llamadas salientes.
*    **Tipo de llamada** indica si la llamada era una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamadas que puede ver son: 

     **Tipos de llamadas a planes de llamadas** 
     *    **user_in** (el usuario recibió una llamada RTC entrante) 
     *    **user_out** (el usuario colocó una llamada RTC saliente) 
     *    **user_out_conf** (el usuario agregó 2 o más participantes de la RTC a la llamada, como una llamada en Conferencia de 3 vías). 
     *    **user_out_transfer** (el usuario transfirió la llamada a un número RTC) 
     *    **user_out_forwarding** (el usuario ha desviado la llamada a un número RTC)

     **Tipos de llamadas de audioconferencia**
     *    **conf_in** (una llamada entrante al puente de audioconferencia) 
     *    **conf_out** (una llamada saliente del puente de audioconferencia suele agregar un número RTC a la Conferencia)

     **Aplicaciones de comunicaciones unificadas (UCAP)** 
     *    **ucap_in** (una llamada RTC entrante a la aplicación de comunicaciones unificadas, como el operador automático o la cola de llamadas) 
     *    **ucap_out** (una llamada RTC saliente de la aplicación de comunicaciones unificadas, como el operador automático o la cola de llamadas)
     *    **Nota:** Las llamadas que se transfirieron a un usuario desde la aplicación de comunicaciones unificadas, como un operador automático o una cola de llamadas, no aparecerán en el informe de uso de RTC, ya que las llamadas de audio de par a par (P2P). Puede acceder a las llamadas de P2P en el centro de administración de Skype empresarial en "herramientas > de análisis de llamadas de Skype empresarial" y buscar por nombre de usuario o dirección SIP correlacionando la llamada por fecha y hora, o de CLID (ID. de línea de llamada). 
*     
     **Nacional/internacional** indica si la llamada que se colocó se consideró nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario. 
*    **Destino marcado** es el nombre del destino del país o la región que se marca como Francia, Alemania o Estados Unidos (EE. UU.). 
*    **Tipo de número** es el tipo de número de teléfono del número de teléfono de un usuario, un servicio o un número gratuito.  
*    **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. 
*    **Duración** muestra el tiempo durante el cual ha estado conectada la llamada.  
*    **ConfID** es el identificador de conferencia de la Conferencia de audio. 
*    **Cargo** es la cantidad de dinero o coste de la llamada que se cobra a tu cuenta. 
*    **Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. 
*    **Capacidad** es la licencia que se usa para la llamada. Los tipos de licencia que puede ver son: 
     *    **MCOPSTNPP** -créditos de comunicaciones <br/> Plan de llamadas **MCOPSTN1** -nacionales (3000 min Estados unidos/1200 mín. planes de la UE) 
     *    Plan de llamadas **MCOPSTN2** -International 
     *    Plan de llamadas **MCOPSTN5** -nacionales (120) 
     *    Plan de llamadas **MCOPSTN6** -nacionales (240 plan de llamadas mín) Nota: disponibilidad limitada
     *    **MCOMEETADD** : audioconferencia
     *    Videoconferencias por minuto de **MCOMEETACPEA**
> [!NOTE]
> Si desea ejecutar un informe para incluir solo las llamadas de pago por minuto que no están incluidas en su suscripción de llamadas o conferencias, filtre el informe con la capacidad de "MCOPSTNPP". Si lo haces, proporcionarás un artículo de todas las llamadas de pago por minuto.  Para las conferencias de audio por minuto de pago, filtrar por "MCOMEETACPEA" en lugar de "MCOPSTNPP".  
***
> [!NOTE]
> También puede ver "sin datos" en algunos campos. "Sin datos" significa que el campo no es aplicable al tipo o la función de la llamada. 
***
> [!NOTE]
> Si tiene un plan de llamadas de Telstra, no verá ningún registro de detalles de llamadas en el informe de uso de RTC. Comunícate con Telstra para tus necesidades de informes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***
![Número 3](../images/sfbcallout3.png)<br/>También puede exportar los datos del informe a un archivo de Excel delimitado por TABULAciones; para ello, haga clic o toque en el botón **exportar a Excel** . Puede exportar datos hasta un año a partir de la fecha actual.<br/><br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de actividad de Skype empresarial](activity-report.md) Puede ver cuánto están usando las sesiones de conferencia punto a punto, organizada y de participación.
    
- [Informe de uso de dispositivos de Skype empresarial](device-usage-report.md) Puede ver los dispositivos que incluyen sistemas operativos basados en Windows y dispositivos móviles que tienen instalada la aplicación Skype empresarial y la usan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype empresarial](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios las conferencias que usan la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones, la web,/dial fuera de terceros y/dial, Microsoft.
    
- [Informe de actividad de participantes de conferencias de Skype empresarial](conference-participant-activity-report.md) Puede ver el número de participantes de la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones, la web y las conferencias de llamadas de llamada.
    
- [Informe de actividad punto a punto de Skype empresarial](peer-to-peer-activity-report.md) Puede ver cuánto usan los usuarios la mensajería instantánea, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de usuarios bloqueados de Skype empresarial](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.

- [Informe de grupos de minutos RTC de Skype empresarial](pstn-minute-pools-report.md) puede ver el número de minutos consumidos durante el mes en curso en la organización.

- [Informe de detalles de sesión de Skype empresarial](session-details-report.md) Puede ver los detalles de las experiencias de llamadas de los usuarios individuales.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
