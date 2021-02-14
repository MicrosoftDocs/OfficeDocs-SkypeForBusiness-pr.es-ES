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
description: El nuevo área informes del Centro de administración de Skype Empresarial muestra la actividad de llamadas y audioconferencias de su organización. Le permite explorar en profundidad los informes para darle una visión más granular de las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de Audioconferencia, incluido el costo de la llamada, para que pueda comprender los detalles de facturación de llamadas y uso para determinar el uso dentro de su organización.
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201174"
---
# <a name="pstn-usage-report"></a>Informe de uso de RTC

El nuevo área informes del Centro de administración **de** Skype Empresarial muestra la actividad de llamadas y audioconferencias de su organización. Le permite explorar en profundidad los informes para darle una visión más granular de las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de Audioconferencia, incluido el costo de la llamada, para que pueda comprender los detalles de facturación de llamadas y uso para determinar el uso dentro de su organización.
  
Consulte la información [general de los informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver más informes que están disponibles.
  
Este informe, junto con los demás informes de Skype Empresarial, le ofrece detalles sobre la actividad, incluido el uso de llamadas en toda su organización. Estos detalles son muy útiles para investigar, planificar y tomar otras decisiones empresariales para su organización, así como para configurar [créditos de comunicaciones.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

- Vaya al Centro de administración > **Centro** de administración de Skype Empresarial para ver los detalles de uso de  >    >    >  **RTC de informes.**
    
    > [!NOTE]
    > Según la suscripción a Microsoft 365 u Office 365 que tenga, es posible que no vea todos los productos e informes que se muestran aquí.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
[![Informe de uso de RTC de Skype Empresarial ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Se muestran todos los usuarios que tienen Skype Empresarial asignado y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    **El identificador de** llamada es el identificador de llamada de una llamada. Es un identificador de la llamada que se usa al llamar al soporte técnico de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **El número de** teléfono es el número de teléfono de Skype Empresarial que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes.
*    **La ubicación del** usuario es el país o la región donde se encuentra el usuario.
*    Identificación **de** llamadas es el número de teléfono (identificación de llamadas) de las llamadas entrantes, el número a partir del cual se originó la llamada o el número de Skype Empresarial desde el que se originó la llamada para las llamadas salientes.
*    **El tipo** de llamada es si la llamada era una llamada entrante o saliente de RTC y el tipo de llamada, como una llamada realizada por un usuario o una audioconferencia. Los tipos de llamada que puede ver son: 

     **Tipos de llamadas del plan de llamadas** 
     *    **user_in** (el usuario ha recibido una llamada RTC entrante) 
     *    **user_out** (el usuario ha realizado una llamada RTC saliente) 
     *    **user_out_conf** (el usuario ha agregado 2 o más participantes de RTC a la llamada, como una llamada de conferencia 3 vías) 
     *    **user_out_transfer** (el usuario ha transferido la llamada a un número DE RTC) 
     *    **user_out_forwarding** (el usuario reenvía la llamada a un número DE RTC)

     **Tipos de llamada de Audioconferencia**
     *    **conf_in** (una llamada entrante al puente de Audioconferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **Id.** de usuario corresponde al organizador de la reunión.
     *    **conf_out** (una llamada saliente desde el puente de Audioconferencia, normalmente para agregar un número de RTC a la conferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **Id.** de usuario corresponde al organizador de la reunión.

     **Aplicaciones de comunicación unificadas (UCAP)** 
     *    **ucap_in** (una llamada RTC entrante a la aplicación de UC, como un operador automático o una cola de llamadas) 
     *    **ucap_out** (una llamada RTC saliente desde la aplicación de UC, como un operador automático o una cola de llamadas)
         > [!NOTE]
         > Las llamadas que se han transferido a un usuario desde la aplicación de UC, como un operador automático o una cola de llamadas, no aparecerán en el informe de uso de RTC, ya que estas llamadas se muestran como llamadas de punto a punto (P2P). Puede acceder a las llamadas P2P del Centro de administración de Skype Empresarial en "Herramientas > Análisis de llamadas de Skype Empresarial" y buscar por nombre de usuario o dirección SIP que correlaciona la llamada por fecha/hora o por origen (identificador de línea de llamada). 

     **Domestic/International** tells you whether the call that was placed was considered domestic (within a country/region) or international (outside of a country/region) based on the user's location. 
*    **El destino marcado** es el nombre del destino del país o región que se marca como Francia, Alemania o Estados Unidos (EE. UU.). 
*    **Tipo de** número es el tipo de número de teléfono que es del número de teléfono de un usuario, un servicio o un número gratuito.  
*    **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. 
*    **Duración** muestra el tiempo durante el cual ha estado conectada la llamada.  
*    **ConfID** es el id. de conferencia de la audioconferencia. 
*    **El** cargo es la cantidad de dinero o el costo de la llamada que se cargará en tu cuenta. 
*    **Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. 
*    **La funcionalidad** es la licencia usada para la llamada. Los tipos de licencia que puede ver son: 
     *    **MCOPSTNPP-** Créditos de comunicaciones <br/> **MCOPSTN1** - Plan de llamadas nacionales (3000 min para EE. UU. /1200 min en planes de la UE) 
     *    **MCOPSTN2** - Plan de llamadas internacionales 
     *    **MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 min) 
     *    **MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 min) Nota: Disponibilidad limitada
     *    **MCOMEETADD** - Audioconferencia
     *    **MCOMEETACPEA** - Audioconferencia de pago por minuto
     
> [!NOTE]
> Si desea ejecutar un informe para incluir solo las llamadas de pago por minuto que no están incluidas en su suscripción de llamada o conferencia, filtre el informe con la función "MCOPSTNPP". Si lo hace, se proporcionará una descripción de todas las llamadas de pago por minuto.  Para pagar audioconferencias por minuto, filtre por "MCOMEETACPEA" en lugar de por "MCOPSTNPP".  

> [!NOTE]
> También es posible que vea "sin datos" en algunos campos. "Sin datos" significa que el campo no se puede aplicar al tipo de llamada o a la capacidad. 

> [!NOTE]
> Si tiene un plan de llamadas de Telstra o Softbank, no verá registros de detalles de las llamadas en el informe de uso de RTC. Ponte en contacto con Telstra o Softbank para ver tus necesidades de informes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportar informe de uso de RTC

Hacer clic o pulsar **el botón Exportar** a Excel le permite descargar el informe de uso de RTC. Puede exportar datos hasta un año desde la fecha actual, a menos que las normativas específicas del país prohíban la conservación de los datos durante 12 meses.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis.

El proceso de exportación puede tardar entre unos pocos segundos y varios minutos en completarse, dependiendo de la cantidad de datos. Cuando el servidor complete la exportación, recibirás un archivo zip denominado "**Llamadas.Export.[ `identifier` ]. zip**", con el identificador como un identificador único de la exportación, que se puede usar para la solución de problemas.

Si tiene planes de llamadas y enrutamiento directo, el archivo exportado puede contener datos de ambos productos. El archivo de informe de uso de RTC tendrá el nombre de archivo "**RTC.calls.[ `UTC date` ]. CSV**". Además de los archivos de enrutamiento directo y RTC, el archivo contiene el archivo **"parameters.js**", con el intervalo de tiempo de exportación seleccionado y las capacidades (si los hay).

El archivo exportado es un archivo de valores separados por comas (CSV), que cumple con [el estándar RFC 4180.](https://tools.ietf.org/html/rfc4180) El archivo se puede abrir en Excel o en cualquier otro editor que cumpla con los estándares sin necesitar transformaciones.

La primera fila del ARCHIVO CSV contiene los nombres de columna.

### <a name="fields-in-the-export"></a>Campos en la exportación

El archivo exportado contiene campos adicionales que no están disponibles en el informe en línea. Pueden usarse para solucionar problemas y flujos de trabajo automatizados.

> [!div class="has-no-wrap"]  
> | #  | Nombre | [Tipo de datos (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador único de llamada |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | Id. de la audioconferencia |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Llamar al id. de usuario en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente es la misma que la dirección SIP del usuario y puede ser la misma que la dirección de correo electrónico del usuario |
> | 6 | Nombre para mostrar de usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que recibió la llamada para llamadas entrantes o el número marcado para las llamadas salientes. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de llamada | `nvarchar(32)` | Si la llamada era una llamada entrante o saliente con RTC y el tipo de llamada, como una llamada realizada por un usuario o una audioconferencia |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | 10 | Nacional/Internacional | `nvarchar(16)` | Si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | 11 | Destino marcado | `nvarchar(64)` | País o región marcados |
> | 12 | Número de destino | `nvarchar(32)` | Número marcado en [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de la llamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duration Seconds | `int` | Cuánto tiempo estuvo conectada la llamada |
> | 16 | Tarifa de conexión | `numeric(16, 2)` | Precio del cargo por conexión |
> | 17 | Cargar | `numeric(16, 2)` | Cantidad de dinero o coste de la llamada que se cargará a tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda usada para calcular el costo de la llamada[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funcionalidad | `nvarchar(32)` | La licencia usada para la llamada |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Informe de actividad de Skype Empresarial](activity-report.md) Puede ver cuánto utilizan sus usuarios las sesiones de conferencia punto a punto, organizadas y participadas.
    
- [Informe de uso de dispositivos de Skype Empresarial](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación de Skype Empresarial instalada y que lo utilizan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype Empresarial](conference-organizer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones, la Web, /dial out - terceros y /dial out - Microsoft.
    
- [Informe de actividad de participantes de conferencias de Skype Empresarial](conference-participant-activity-report.md) Puede ver en cuántas conferencias de audio de mi, audio/vídeo, uso compartido de aplicaciones, web y de llamada están participando.
    
- [Informe de actividad punto a punto de Skype Empresarial](peer-to-peer-activity-report.md) Puede ver cuánto utilizan sus usuarios la MI, el audio/vídeo, el uso compartido de aplicaciones y la transferencia de archivos.
    
- [Informe de usuarios bloqueados de Skype Empresarial](users-blocked-report.md) Puede ver los usuarios de su organización a los que se les ha bloqueado la realización de llamadas RTC.

- [El informe de los grupos de](pstn-minute-pools-report.md) minutos RTC de Skype Empresarial permite ver el número de minutos consumidos durante el mes actual dentro de su organización.

- [Informe de detalles de la sesión de Skype Empresarial](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividades en el centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
