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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: El nuevo área informes del centro de administración de Skype empresarial muestra la actividad de llamadas y audioconferencias en su organización. Le permite profundizar en los informes para proporcionarle información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de conferencias de audio, incluido el costo de la llamada, para que pueda comprender su uso y los detalles de facturación para determinar el uso dentro de su organización.
ms.openlocfilehash: e298bc79b821a8ec8373186a879b94790bc9d151
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918518"
---
# <a name="pstn-usage-report"></a>Informe de uso de RTC

El nuevo área **informes** del centro de administración de Skype empresarial muestra la actividad de llamadas y audioconferencias en su organización. Le permite profundizar en los informes para proporcionarle información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de conferencias de audio, incluido el costo de la llamada, para que pueda comprender su uso y los detalles de facturación para determinar el uso dentro de su organización.
  
Consulte la [información general](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) de los informes para ver más informes que están disponibles.
  
Este informe, junto con los otros informes de Skype empresarial, ofrece detalles sobre la actividad, lo que incluye el uso en toda la organización. Estos detalles son muy útiles para investigar, planear y tomar otras decisiones empresariales para su organización y para configurar [créditos de comunicaciones](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Puede ver todos los informes de Skype empresarial cuando inicia sesión como administrador en el centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

- Vaya al centro de administración > **centros** > de administración > **centro de administración de Skype empresarial****informa** > de los**detalles de uso de RTC**.
    
    > [!NOTE]
    > Según la suscripción de Microsoft 365 u Office 365 que tenga, es posible que no vea todos los productos e informes que se muestran aquí.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Informe de uso de RTC de Skype Empresarial](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Se muestran todos los usuarios que tienen Skype empresarial asignado y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    El **identificador de llamada** es el identificador de llamada de una llamada. Es un identificador de la llamada que se usa al llamar a soporte técnico de servicios de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **Número de teléfono** es el número de teléfono de Skype para empresas que recibió la llamada para llamadas entrantes o el número marcado para llamadas salientes.
*    **Ubicación del usuario** es el país o la región donde se encuentra el usuario.
*    La **identificación de llamadas** es el número de teléfono de la persona que llama (identificador de la llamada) para las llamadas entrantes, el número desde el que se originó la llamada o el número de Skype empresarial desde el que se originó la llamada para llamadas salientes.
*    **Tipo de llamada** indica si la llamada era una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamadas que puede ver son: 

     **Tipos de llamadas a planes de llamadas** 
     *    **user_in** (el usuario recibió una llamada RTC entrante) 
     *    **user_out** (el usuario hizo una llamada RTC saliente) 
     *    **user_out_conf** (el usuario agregó 2 o más participantes de la RTC a la llamada, como una llamada en Conferencia de 3 vías) 
     *    **user_out_transfer** (el usuario transfirió la llamada a un número de RTC) 
     *    **user_out_forwarding** (el usuario ha desviado la llamada a un número RTC)

     **Tipos de llamadas de audioconferencia**
     *    **conf_in** (una llamada entrante al puente de audioconferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **identificador de usuario** corresponde al organizador de la reunión.
     *    **conf_out** (una llamada saliente del puente de conferencias de audio, generalmente para agregar un número RTC a la Conferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **identificador de usuario** corresponde al organizador de la reunión.

     **Aplicaciones de comunicaciones unificadas (UCAP)** 
     *    **ucap_in** (una llamada RTC entrante a la aplicación de comunicaciones unificadas, como el operador automático o la cola de llamadas) 
     *    **ucap_out** (una llamada RTC saliente de la aplicación de comunicaciones unificadas, como un operador automático o una cola de llamadas)
         > [!NOTE]
         > Las llamadas que se transfirieron a un usuario desde la aplicación de comunicaciones unificadas, como un operador automático o una cola de llamadas, no aparecerán en el informe de uso de RTC, ya que las llamadas de audio de par a par (P2P). Puede acceder a las llamadas de P2P en el centro de administración de Skype empresarial en "herramientas > de análisis de llamadas de Skype empresarial" y buscar por nombre de usuario o dirección SIP correlacionando la llamada por fecha y hora, o de CLID (ID. de línea de llamada). 

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

> [!NOTE]
> También puede ver "sin datos" en algunos campos. "Sin datos" significa que el campo no es aplicable al tipo o la función de la llamada. 

> [!NOTE]
> Si tiene un plan de llamadas de Telstra, no verá ningún registro de detalles de llamadas en el informe de uso de RTC. Comunícate con Telstra para tus necesidades de informes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportar informe de uso de RTC

Hacer clic o pulsar el botón **exportar a Excel** le permite descargar el informe de uso de RTC. Puede exportar datos hasta un año a partir de la fecha actual, a menos que las regulaciones específicas del país prohíban la retención de los datos por 12 meses.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis.

El proceso de exportación puede tardar entre unos segundos y varios minutos en completarse, dependiendo de la cantidad de datos. Cuando el servidor complete la exportación, recibirá un archivo zip denominado "**calls. Export. [ ] `identifier`. zip**", donde el identificador es un identificador único para la exportación, que se puede usar para la solución de problemas.

Si tiene tanto planes de llamadas como enrutamiento directo, el archivo exportado puede contener datos para ambos productos. El archivo de informe de uso de RTC tendrá el nombre de archivo "**RTC. calls. [ ] `UTC date`. csv**". Además de los archivos RTC y de enrutamiento directo, el archivo contiene "**Parameters. JSON**", con el intervalo de tiempo de exportación seleccionado y las funcionalidades (si las hay).

Archivo exportado es un archivo de valores separados por comas (CSV), compatible con el estándar [RFC 4180](https://tools.ietf.org/html/rfc4180) . El archivo se puede abrir en Excel o en cualquier otro editor conforme a los estándares sin necesidad de ninguna transformación.

La primera fila del archivo CSV contiene nombres de columna.

### <a name="fields-in-the-export"></a>Campos en la exportación

Archivo exportado contiene campos adicionales que no están disponibles en el informe en línea. Se pueden usar para la solución de problemas y los flujos de trabajo automatizados.

> [!div class="has-no-wrap"]  
> | #  | Nombre | [Tipo de datos (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | ,0 | UsageId | `uniqueidentifier` | Identificador de llamada único |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | IDENTIFICADOR de la Conferencia de audio |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Prefijo internacional del usuario, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | ObjectId de AAD | `uniqueidentifier` | Llamando al identificador de usuario en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamada de Bot (ucap_in, ucap_out) |
> | 5 | PRINCIPAL | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente es el mismo que la dirección SIP del usuario y puede ser igual a la dirección de correo electrónico del usuario. |
> | 6 | Nombre para mostrar del usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que recibió la llamada de llamadas entrantes o el número marcado para llamadas salientes. Formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
> | 4,8 | Tipo de llamada | `nvarchar(32)` | Si la llamada fue una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio |
> | 99,999 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | base10 | Nacional o internacional | `nvarchar(16)` | Si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | once | Destino marcado | `nvarchar(64)` | País o región marcados |
> | 2007 | Número de destino | `nvarchar(32)` | Número marcado en formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de la llamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 4,5 | Segundos de duración | `int` | Cuánto tiempo se conectó la llamada |
> | apartado | Cargo por conexión | `numeric(16, 2)` | Precio de la tarifa por conexión |
> | apartado | Cargas | `numeric(16, 2)` | Cantidad de dinero o coste de la llamada que se cobra a tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda que se usa para calcular el costo de la llamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Función | `nvarchar(32)` | La licencia usada para la llamada |

    
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
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
