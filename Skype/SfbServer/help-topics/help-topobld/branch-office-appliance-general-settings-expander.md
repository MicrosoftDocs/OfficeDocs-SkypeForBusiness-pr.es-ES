---
title: Expansor de configuración general de aplicación de sucursal
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para modificar la configuración de un dispositivo de sucursal que sobreviven o servidor de la sucursal que sobreviven existente, se presentan con las siguientes secciones:'
ms.openlocfilehash: 1f0c1b47d0ea042f29172f4557ef78db42f83216
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de configuración general de aplicación de sucursal
 
Para modificar la configuración de un dispositivo de sucursal que sobreviven o servidor de la sucursal que sobreviven existente, se presentan con las siguientes secciones:
  
- Configuración general
    
- Configuración de resistencia
    
- Configuración del servidor de mediación
    
## 

Un equipo de sucursal que sobreviven o de servidor de sucursal que sobreviven, se presentan con lo siguiente:
  
### <a name="general-settings"></a>Configuración general

El nombre de dominio completo (FQDN) del servidor de sucursal que sobreviven o dispositivo de sucursal que sobreviven. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
Puede seleccionar **Usar todas las direcciones IP configuradas** o **Limitar el uso del servicio a las direcciones IP seleccionadas**. Si selecciona **Limitar el uso del servicio a las direcciones IP seleccionadas**, definirá la dirección IP principal que el servidor usará para todas las comunicaciones, excepto para la puerta de enlace de la red de telefonía conmutada (RTC). Para la RTC se define otra dirección IP.
  
En **Asociaciones**, puede editar o especificar lo siguiente:
  
- Servidor de archivado asociado permite Seleccione esta opción para asociar el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven en un servidor de archivado. Puede seleccionar desde un servidor de archivado ya definido seleccionando el servidor de la lista desplegable o haga clic en **nuevo** y especifique un nuevo servidor de archivado.
    
    > [!IMPORTANT]
    > Antes de publicar la topología recién definida, el servidor que especifique tiene que existir y estar unido al dominio. 
  
- Asociar el servidor de supervisión permite Seleccione esta opción para asociar el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven en un servidor de supervisión. Puede seleccionar desde un servidor de supervisión ya definido seleccionando el servidor de la lista desplegable o haga clic en **nuevo** y especifique un nuevo servidor de supervisión.
    
- Asociar el grupo permite seleccionar para asociar un servidor perimetral o grupo con el que sobreviven dispositivo de sucursal o servidor de sucursal que sobreviven el borde. Puede elegir un servidor perimetral o un grupo de servidores perimetrales que ya esté definido seleccionándolo en la lista desplegable o hacer clic en **Nuevo** para especificar un servidor perimetral o grupo de servidores perimetrales nuevo.
    
### <a name="resiliency"></a>Resistencia

La resistencia proporciona una gran disponibilidad al grupo de registradores. Al proporcionar un registrador de copia de seguridad, si el primer registrador falla, el registrador de copia de seguridad puede reemplazar al que ha fallado de modo que los usuarios puedan seguir registrándose y comunicándose. Es posible que algunos usuarios tengan una funcionalidad reducida según los sistemas que hayan fallado con el registrador principal.
  
En la lista desplegable, seleccione el grupo de servidores Front-End de Enterprise Edition o Standard Edition servidor Front-End que actuará como el registrador de la copia de seguridad para el dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven. También puede habilitar intervalos de tiempo de conmutación por error y conmutación por recuperación. Al habilitar la configuración de tiempo de conmutación por error y la conmutación por recuperación (lo que se especifica en segundos), se habilita la detección automática de registradores erróneos y un tiempo de conmutación por recuperación que permite la determinación automática que el registrador principal vuelve a estar recuperado y puede retomar el proceso del registrador.
  
> [!IMPORTANT]
> Al definir la detección de fallos y el intervalo de conmutación por recuperación, tenga mucho cuidado de no introducir un intervalo que provoque la ejecución de la conmutación por error y por recuperación en el caso que el registrador no logre responder durante un espacio breve de tiempo. Es posible que el registrador principal no responda durante breves periodos de tiempo en función de la carga de los grupos o servidores. Los valores predeterminados para un dispositivo de la rama que sobreviven o un servidor de sucursal que sobreviven en un sitio a un grupo o Front End un servidor Standard Edition es de 120 segundos para la conmutación por error y 240 segundos para reserva. 
  
### <a name="mediation-server"></a>Servidor de mediación

Puede especificar lo siguiente en relación con un **servidor de mediación**:
  
La casilla de verificación **habilitado servidor de mediación ubicados** no está disponible en un dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven porque está ubicado en el servidor de mediación.
  
Defina el puerto de escucha de los servidores del grupo para Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesitará definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.
  
Definir puertas de enlace PSTN que están asociados con el servidor de mediación colocadas. Si ya ha definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación. Si no ha definido ninguna puerta de enlace, pero hay disponibles para definirlas, puede seleccionar **Nuevo**. También puede quitar las puertas de enlace que ya están configuradas para este servidor de mediación. Seleccione la puerta de enlace y, luego, haga clic en **Quitar**.
  
Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la puerta de enlace predeterminada. Si tiene que elegir otra puerta de enlace como predeterminada, seleccione la que quiera y, luego, haga clic en **Establecer como predeterminado**.
  
### 

Para obtener más información sobre cómo definir y configurar las opciones para el dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven, vea [Soluciones de resiliencia del sitio de sucursal](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).
  

