---
title: Uso compartido de pantallas basado en vídeo para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Información de planeación y configuración de Skype Empresarial Server para uso compartido de pantalla basado en vídeo (VbSS)
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103066"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Uso compartido de pantallas basado en vídeo para Skype Empresarial Server 
 
El uso compartido de pantalla basado en vídeo (VbSS) en Skype Empresarial Server 2015 ya está disponible para su descarga: Actualización acumulativa de [Skype Empresarial Server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS se incluye con Skype Empresarial Server 2019.
  
El uso compartido de pantalla basado en vídeo, o VbSS, surgió del uso compartido de pantalla de Lync. La diferencia entre VbSS y el uso compartido de pantalla tradicional tiene que ver con los protocolos subyacentes usados y con lo que destacan. El uso compartido de pantalla usa el protocolo de escritorio remoto (RDP), que es excelente para crear miles de sesiones de 1 a 1 entre los equipos de las personas. La tecnología más reciente, VbSS, usará el Protocolo de datagramas de usuario (UDP).
  
Skype Empresarial Server quería mejorar las experiencias de reuniones y conversaciones de 1 a 1 de las personas y de 1 a varios (varias partes). VbSS usa la plataforma multimedia (que se basa en UDP como protocolo subyacente), con el objetivo de mejorar los tiempos de inicio del vídeo, la calidad de visualización de lo que está viendo (especialmente si lo que está viendo se mueve rápidamente) y la confiabilidad en general.
  
Parte del objetivo de mejorar el uso compartido de pantalla es que las transiciones entre VbSS y RDP sean lo más fluidas posible cuando se produzcan. Dado que VbSS es una actualización de la tecnología subyacente que se usa en el uso compartido de pantalla para Skype Empresarial Server, puede resultar difícil detectar qué tecnología está aprovechando a menos que esté viendo detalles SIP en el tráfico de red o esté compartiendo contenido que se mueve rápidamente o 3D. Si, por ejemplo, su lugar de trabajo tiene una gran cantidad de clientes heredados, RDP seguirá estando disponible como un entorno seguro para las reuniones y conversaciones. Skype Empresarial Server usa lógica interna para decidir cuál de los dos métodos (VbSS o uso compartido de pantalla tradicional) se aplicará cuando los clientes se conecten. RDP puede y se sustituirá por VbSS cuando la situación lo llame, de modo que no se interrumpa la experiencia de visualización.
  
## <a name="planning"></a>Planificación

### <a name="vbss-pros-and-cons"></a>Ventajas y desventajas de VbSS

Cambiar a VbSS tiene como objetivo realizar tres mejoras clave:
  
1. Hacer uso compartido de pantalla (hasta un 5 %) más confiable en comparación con RDP solo.

2. Haga que la configuración de la sesión y la experiencia de vídeo sea más rápida en comparación con RDP solo (configuración en la mitad del tiempo, con una mejora de 6:1 en fotogramas por segundo).

3. Funciona mucho mejor que RDP en condiciones de ancho de banda bajo, incluso cuando se comparte contenido de alto movimiento, como gráficos 3D.
    
Tenga en cuenta que estos números dependen del estado y el ajuste adecuado del rendimiento de la red, y pueden implicar redes externas a las suyas, si sus clientes están en dispositivos móviles.
  
También debe tener en cuenta que se ha negociado cierta fidelidad o nítido del contenido compartido por confiabilidad, velocidad y eficacia. En la mayoría de los casos, esto no será fácilmente visible para los usuarios.
  
### <a name="ports-and-protocols"></a>Puertos y protocolos

**Puertos de servidor necesarios**

|**Rol del servidor**|**Nombre del servicio**|**Intervalo de puertos o puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype Empresarial Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype Empresarial Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de puerto de medios usado para compartir aplicaciones.  <br/> |
   
**Puertos de cliente necesarios**

|**Componente**|**Intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Uso compartido de aplicaciones.  <br/> |
   
Si QoS está habilitado para los siguientes puertos multimedia y VbSS también está habilitado, durante una conferencia que incluya el uso compartido de escritorio, la MCU de AS usará la configuración de puerto de vídeo que se muestra en negrita a continuación para el tráfico compartido de pantalla. 
  
> [!IMPORTANT]
> Esta configuración es un caso especial y esta configuración exacta debe usarse al implementar ambas características. Esto invalida otras opciones recomendadas en la [documentación de QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos). Para el uso compartido de aplicaciones, también deberá especificar ASMCUSVC.exe en el GPO de QoS además de definir estos valores de puerto. 
  
**Configuración necesaria de QoS/VbSS de Application Server**

|**Propiedad**|**Valor de puerto**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planeamiento de capacidad

Cada servidor front-end que ejecute Skype Empresarial Server 2015 cumulative update 2 (CU2) o posterior admite hasta 375 participantes para el uso compartido de pantalla con RDP (aunque solo 250 por reunión). Esta capacidad no cambia después de CU3, cuando se introduce y se usa VbSS.
  
Dicho esto, hemos realizado pruebas de rendimiento y esfuerzo en nuestro laboratorio, y las siguientes medidas también deben tenerse en cuenta con respecto a su propia implementación (según el uso, por supuesto).
  
Suponiendo que:
  
- Está usando Skype Empresarial Server 2015 CU2 o posterior en la implementación.
    
- Todos los usuarios del entorno de Skype Empresarial Server tienen resoluciones de pantalla superiores a 1920 x 1080.
    
A plena capacidad (que, como se mencionó anteriormente, es de 375 participantes de uso compartido de pantalla por servidor front-end en total, aunque solo 250 por reunión), el servidor front-end puede usar ~89 % de los 1 Gigabit de la tarjeta de red. Esto se debe a que la tecnología de uso compartido de pantalla existente en Skype Empresarial Server CU2 (RDP) transmite el contenido en pantalla a la resolución nativa del equipo del moderador. Por lo tanto, con las resoluciones de pantalla más altas, es posible que ya esté experimentando cuellos de botella de red para el uso compartido de pantalla con Skype Empresarial Server 2015 CU2.
  
Para mitigar esto, una o varias de las siguientes opciones pueden ser útiles:
  
- Actualice el servidor front-end de una tarjeta de red de 1 Gigabit a una tarjeta Ethernet de 10 Gigabit.

- Aumente el número de servidores front-end para equilibrar el tráfico.

- Limite el ancho de banda (velocidad de bits) usado para VbSS y RDP colocando un límite en el ancho de banda máximo usado por ambos canales.
    
Los números de esta tabla están influenciados por redes individuales y por el contenido que se comparte. Pruebe para establecer líneas base para su red o redes.
  
|**Contenido de 1080p**|**Promedio DE RDP**|**Pico DE RDP**|**Promedio de VbSS**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps  <br/> |12mbps  <br/> |100 kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3mbps  <br/> |2,2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia

El ancho de banda de VbSS es:
  
|**Códec de video**|**Resolución y relación de aspecto**|**Velocidad de bits de carga máxima de vídeo (Kbps)**|**Velocidad mínima de bits de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (La relación de aspecto depende de la resolución del monitor del sharer y no siempre será de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Compatibilidad con clientes y servidores

El uso compartido de pantalla basado en vídeo requiere Skype Empresarial Server 2015 CU3 o posterior, y una versión actual de los clientes compatibles que aparecen en la comparación de características de cliente móvil para la compatibilidad con [Skype](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) Empresarial y [reuniones.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
Hay situaciones en las que el uso compartido de pantalla pasará a RDP, como estas:
  
- Si la cuenta está hospedada en un entorno donde asmcu no cumple la compilación mínima compatible con VbSS.
- Si alguien que usa una versión anterior del cliente de Skype Empresarial se une a la sesión, por ejemplo, cualquier persona que use cualquier versión de cliente de Windows inferior a 16.0.6330.1000, Dispositivos del sistema de salón de Skype Empresarial o Aplicaciones móviles de Skype Empresarial. 
- Si un usuario está compartiendo desde la aplicación web de Skype Empresarial.
- Si alguien usa Skype Empresarial en Mac y no está en Skype Empresarial Online o Skype Empresarial Server 2015 con la actualización acumulativa de julio de 2018 (o posterior).
- Si alguien inicia cualquier programa o Uso compartido de Windows.
- Si alguien empieza a grabar la sesión.
- Si alguien invoca el Control remoto de pantalla durante la sesión. 
- Reuniones con más de 250 participantes (donde VbSS no es compatible actualmente).

Tenga en cuenta que una vez que la sesión pasa a RDP, no volverá a realizar la transición a VbSS. De nuevo, la transición desde VbSS está pensada para ser fluida y, con la esperanza, no será fácil de detectar en la mayoría de las situaciones.
    
> [!NOTE]
> No se admite bloquear o intentar bloquear la transición de VbSS a RDP en el uso compartido de pantalla de Skype Empresarial. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, deshabilitar y configurar VbSS

Lo bueno es que, una vez que haya instalado la actualización acumulativa de Skype Empresarial Server 2015 3 (CU3) o posterior, todos los usuarios estarán habilitados para VbSS de 1 a 1 y de varias partes de forma predeterminada. Esto puede ser problemático para usted si tiene una razón para no tener esta funcionalidad habilitada para todos los usuarios. En ese caso, puede usar estos pasos para deshabilitar a los usuarios (los pasos de habilitar usuarios seguirán):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Cómo deshabilitar que los usuarios usen VbSS

- Puede asignar una directiva de usuario que no permita VbSS a los usuarios que no deberían usar VbSS ejecutando este cmdlet en la Consola de administración de Skype Empresarial (reemplace [PolicyName] por la directiva para la que está haciendo esto):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios sin una directiva asignada:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obtener más información sobre este comando, [vea Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita desactivar VbSS completamente, puede ejecutar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obtener más información sobre este comando, [vea Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype Empresarial multiparte, todos los extremos de cliente respetarán la configuración de directiva para el organizador de la reunión. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Cómo permitir que los usuarios usen VbSS

- Puede asignar una directiva de usuario específica que permita VbSS a cualquier usuario que necesite usar VbSS ejecutando este cmdlet en la Consola de administración de Skype Empresarial (reemplace [PolicyName] por la directiva para la que está haciendo esto):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios sin una directiva asignada:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obtener más información sobre este comando, [vea Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita volver a activar VbSS después de desactivarlo (está encendido de forma predeterminada), puede ejecutar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obtener más información sobre este comando, [vea Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype Empresarial de varias partes, todos los extremos de cliente respetarán la configuración de directiva para el organizador de la reunión. 
  
## <a name="see-also"></a>Ver también

[Actualización acumulativa de Skype Empresarial Server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[El uso compartido de pantalla basado en vídeo (VBSS) está disponible en Skype Empresarial Server 2015](https://support.microsoft.com/kb/3170163)