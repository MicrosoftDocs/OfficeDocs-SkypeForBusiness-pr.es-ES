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
description: El nuevo Skype Empresarial de informes del Centro de administración muestra la actividad de llamadas y audioconferencias en su organización. Le permite explorar en profundidad los informes para proporcionar información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe Detalles de uso de RTC de Skype Empresarial para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de audioconferencia, incluido el costo de la llamada para que pueda comprender los detalles de facturación de llamadas y uso para determinar el uso dentro de su organización.
ms.openlocfilehash: 2c6a0410611919662f5eaf37a03bfcca11b543be
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278453"
---
# <a name="pstn-usage-report"></a>Informe de uso de RTC

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

El nuevo área Skype Empresarial informes **del** Centro de administración muestra la actividad de llamadas y audioconferencias en su organización. Le permite explorar en profundidad los informes para proporcionar información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe **Detalles de uso de RTC de Skype Empresarial** para ver el número de minutos dedicados a llamadas entrantes y salientes, así como el coste de dichas llamadas. Puede ver los detalles de uso de RTC de audioconferencia, incluido el costo de la llamada para que pueda comprender los detalles de facturación de llamadas y uso para determinar el uso dentro de su organización.
  
Consulte información general [sobre informes](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obtener más informes disponibles.
  
Este informe, junto con el resto de Skype Empresarial, le proporciona detalles sobre la actividad, incluido el uso de llamadas en toda la organización. Estos detalles son muy útiles al investigar, planear y tomar otras decisiones empresariales para su organización y para configurar créditos [de comunicaciones.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puede ver todos los informes Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

- Vaya al centro de administración > **centros** de administración Skype Empresarial centro de  >  **administración**  >  **Informes de** detalles de uso de  >  **RTC.**
    
    > [!NOTE]
    > Dependiendo de Microsoft 365 o Office 365 suscripción que tenga, es posible que no vea todos los productos e informes que se muestran aquí.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar el informe Uso de RTC de Skype Empresarial

Puede analizar el uso de RTC de Skype Empresarial de sus usuarios consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
[![Skype Empresarial de uso de RTC ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Número 1](../images/sfbcallout1.png)<br/>La tabla muestra un desglose de todo el uso de RTC por usuario. Esto muestra todos los usuarios que Skype Empresarial asignados a ellos y su uso de RTC. Puede agregar o quitar columnas en la tabla.
*    **Id. de** llamada es el id. de llamada de una llamada. Es un identificador para la llamada que se usa al llamar al servicio de soporte técnico de Microsoft.
*    **Identificador de usuario** es el nombre de inicio de sesión del usuario.
*    **Teléfono es** el Skype Empresarial de teléfono que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes.
*    **La ubicación del** usuario es el país o región donde se encuentra el usuario.
*    **Identificador de** llamada es el número de teléfono (Identificador de llamada) de las llamadas entrantes, el número desde el que se originó la llamada o el número de Skype Empresarial desde el que se originó la llamada para las llamadas salientes.
*    **El tipo** de llamada es si la llamada era una llamada rtc saliente o entrante y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamada que puede ver son: 

     **Tipos de llamadas de plan de llamadas** 
     *    **user_in** (el usuario recibió una llamada RTC entrante) 
     *    **user_out** (el usuario ha realizado una llamada RTC saliente) 
     *    **user_out_conf** (el usuario agregó 2 o más participantes RTC a la llamada, como una llamada de conferencia de tres vías) 
     *    **user_out_transfer** (el usuario ha transferido la llamada a un número RTC) 
     *    **user_out_forwarding** (el usuario reenvía la llamada a un número RTC)

     **Tipos de llamadas de audioconferencia**
     *    **conf_in** (una llamada entrante al puente de audioconferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **Id.** de usuario corresponde al organizador de la reunión.
     *    **conf_out** (una llamada saliente desde el puente de audioconferencia, normalmente para agregar un número RTC a la conferencia). Para los registros de este tipo de llamada, el usuario especificado en la columna **Id.** de usuario corresponde al organizador de la reunión.

     **Aplicaciones de comunicación unificada (UCAP)** 
     *    **ucap_in** (una llamada RTC entrante a la aplicación UC como operador automático o cola de llamadas) 
     *    **ucap_out** (una llamada RTC saliente desde la aplicación UC, como operador automático o cola de llamadas)
         > [!NOTE]
         > Las llamadas que se transfirieron a un usuario desde la aplicación UC, como un operador automático o una cola de llamadas, no aparecerán en el informe de uso de RTC, ya que estos tramos de llamada son llamadas de audio punto a punto (P2P). Puede acceder a las llamadas P2P en el Centro de administración de Skype Empresarial en "Herramientas > Skype Empresarial Análisis de llamadas" y buscar por nombre de usuario o dirección SIP correlacionando la llamada por fecha/hora y/o clid de origen (id. de línea de llamada). 

     **Nacionales e** Internacionales le indica si la llamada realizada se consideró nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario. 
*    **Destino marcado es** el nombre del destino país o región que se marca como Francia, Alemania o Estados Unidos (EE.UU.). 
*    **Tipo de** número es el tipo de número de teléfono que se encuentra a partir del número de teléfono de un usuario, un servicio o un número gratuito.  
*    **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. 
*    **Duración** muestra el tiempo durante el cual ha estado conectada la llamada.  
*    **ConfID** es el id. de conferencia de la audioconferencia. 
*    **El** cargo es la cantidad de dinero o costo de la llamada que se está cobrando en tu cuenta. 
*    **Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. 
*    **La funcionalidad** es la licencia que se usa para la llamada. Los tipos de licencia que puede ver son: 
     *    **MCOPSTNPP:** créditos de comunicaciones <br/> **MCOPSTN1** - Plan de llamadas nacionales (3000 min ee. UU. / 1200 min planes de la UE) 
     *    **MCOPSTN2** - Plan de llamadas internacionales 
     *    **MCOPSTN5** - Plan de llamadas nacionales (plan de llamadas de 120 minutos) 
     *    **MCOPSTN6** - Plan de llamadas nacionales (plan de llamadas de 240 min) Nota: Disponibilidad limitada
     *    **MCOMEETADD-** Audioconferencia
     *    **MCOMEETACPEA:** audioconferencia de pago por minuto
     
> [!NOTE]
> Si desea ejecutar un informe para incluir solo las llamadas de pago por minuto que no se incluyen en su suscripción de llamadas o conferencias, filtre el informe con la capacidad "MCOPSTNPP". Al hacerlo, se proporcionará una descripción de todas las llamadas de pago por minuto.  Para las audioconferencias de pago por minuto, filtre por "MCOMEETACPEA" en lugar de "MCOPSTNPP".  

> [!NOTE]
> Es posible que también vea "no hay datos" en algunos campos. "Sin datos" significa que el campo no es aplicable al tipo de llamada o la capacidad. 

> [!NOTE]
> Si tiene un plan de llamadas de Telstra o Softbank, no verá ningún registro de detalles de llamadas en el informe de uso de RTC. Póngase en contacto con Telstra o Softbank para sus necesidades de informes. 
***
![Número 2](../images/sfbcallout2.png)<br/>Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportar informe de uso de RTC

Hacer clic o pulsar el **botón Exportar Excel** permite descargar el informe de uso de RTC. Puede exportar datos hasta un año a partir de la fecha actual, a menos que las normativas específicas del país prohíban la retención de los datos durante 12 meses.

De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis.

El proceso de exportación puede tardar entre unos segundos y varios minutos en completarse, dependiendo de la cantidad de datos. Cuando el servidor complete la exportación, recibirá un archivo zip denominado "**Calls.Export.[ `identifier` ] .zip**", con el identificador como un identificador único para la exportación, que se puede usar para la solución de problemas.

Si tiene planes de llamadas y enrutamiento directo, el archivo exportado puede contener datos para ambos productos. El archivo de informe de uso rtc tendrá el nombre de archivo "**RTC.calls.[ `UTC date` ] .csv**". Además de los archivos RTC y Enrutamiento directo, el archivo contiene el archivo "**parameters.js** en ", con el intervalo de tiempo de exportación seleccionado y las capacidades (si los hay).

El archivo exportado es un archivo de valores separados por comas (CSV), compatible con [el estándar RFC 4180.](https://tools.ietf.org/html/rfc4180) El archivo se puede abrir en Excel o en cualquier otro editor que cumpla los estándares sin necesidad de realizar transformaciones.

La primera fila del ARCHIVO CSV contiene nombres de columna.

### <a name="fields-in-the-export"></a>Campos en la exportación

El archivo exportado contiene campos adicionales que no están disponibles en el informe en línea. Se pueden usar para solucionar problemas y flujos de trabajo automatizados.

> [!div class="has-no-wrap"]  
> | #  | Nombre | [Tipo de datos (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descripción |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador de llamada único |
> | 1 | Id. de llamada | `nvarchar(64)` | Identificador de llamada. No se garantiza que sea único |
> | 2 | Id. de conferencia | `nvarchar(64)` | Id. de la audioconferencia |
> | 3 | Ubicación del usuario | `nvarchar(2)` | Código de país del usuario, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Identificador del usuario que llama en Azure Active Directory.<br/> Esta y otra información de usuario serán nulas o vacías para los tipos de llamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nombre de inicio de sesión) en Azure Active Directory.<br/>Normalmente, esto es lo mismo que la dirección SIP del usuario y puede ser igual que la dirección de correo electrónico del usuario |
> | 6 | Nombre para mostrar de usuario | `nvarchar(128)` | Nombre para mostrar del usuario |
> | 7 | Identificador de llamada | `nvarchar(128)` | Número que recibió la llamada para las llamadas entrantes o el número marcado para las llamadas salientes. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de llamada | `nvarchar(32)` | Si la llamada era una llamada entrante o saliente RTC y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de teléfono del usuario, como un servicio de número gratuito |
> | 10 | Nacional/Internacional | `nvarchar(16)` | Si la llamada era nacional (dentro de un país o región) o internacional (fuera de un país o región) en función de la ubicación del usuario |
> | 11 | Destino marcado | `nvarchar(64)` | País o región marcado |
> | 12 | Número de destino | `nvarchar(32)` | Número marcado en [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de inicio | `datetimeoffset` | Hora de inicio de llamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Hora de finalización | `datetimeoffset` | Hora de finalización de la llamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duración segundos | `int` | Cuánto tiempo estuvo conectada la llamada |
> | 16 | Tarifa de conexión | `numeric(16, 2)` | Precio de la tarifa de conexión |
> | 17 | Cargo | `numeric(16, 2)` | Cantidad de dinero o costo de la llamada que se carga en tu cuenta |
> | 18 | Moneda | `nvarchar(3)` | Tipo de moneda usada para calcular el costo de la llamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funcionalidad | `nvarchar(32)` | La licencia usada para la llamada |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>¿Desea ver otros informes de Skype Empresarial?

- [Skype Empresarial actividad](activity-report.md) Puede ver cuánto usan los usuarios de punto a punto, organizados y participados en sesiones de conferencia.
    
- [Skype Empresarial de uso de dispositivos](device-usage-report.md) Puede ver los dispositivos, incluidos los sistemas operativos basados en Windows y los dispositivos móviles que tienen la aplicación Skype Empresarial instalada y la usan para mensajería instantánea y reuniones.
    
- [Skype Empresarial actividad del organizador de conferencias](conference-organizer-activity-report.md) Puede ver cuánto están organizando los usuarios conferencias que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones, Web, /dial out - terceros y /dial out - Microsoft.
    
- [Skype Empresarial actividad de los participantes de la conferencia](conference-participant-activity-report.md) Puede ver cuántas conferencias de audio, audio y vídeo, uso compartido de aplicaciones, Web y llamadas de audio se están participando en.
    
- [Skype Empresarial de actividad punto a punto](peer-to-peer-activity-report.md) Puede ver la cantidad de usuarios que usan mensajería instantánea, audio/vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Skype Empresarial de usuarios bloqueados](users-blocked-report.md) Puede ver los usuarios de su organización que han sido bloqueados para realizar llamadas RTC.

- [Skype Empresarial de grupos de minutos](pstn-minute-pools-report.md) RTC puede ver el número de minutos consumidos durante el mes actual dentro de su organización.

- [Skype Empresarial detalles de la sesión](session-details-report.md) Puede ver detalles sobre las experiencias de llamada de un usuario individual.
    
## <a name="related-topics"></a>Temas relacionados
[Informes de actividad en el Centro de administración](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
