---
title: Pantalla compartida basada en vídeo para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Información de planeación y configuración de Skype empresarial Server para el uso compartido de pantalla basado en vídeo (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009573"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Pantalla compartida basada en vídeo para Skype empresarial Server 
 
La pantalla compartida basada en vídeo (VbSS) en Skype empresarial Server 2015 ya está disponible para su descarga: [paquete de actualización acumulativa de Skype empresarial server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS se incluye con Skype empresarial Server 2019.
  
El uso compartido de pantalla basado en vídeo, o VbSS, ha extraído del uso compartido de pantalla de Lync. La diferencia entre VbSS y el uso compartido de la pantalla tradicional tiene que conocer los protocolos subyacentes que se usan y lo que hace en Excel. El uso compartido de pantalla usa el protocolo de escritorio remoto (RDP), que es excelente para crear miles de sesiones de 1 a 1 entre los equipos de los usuarios. La tecnología más nueva, VbSS, usará el protocolo de datagramas de usuario (UDP).
  
Skype empresarial Server deseaba mejorar el 1 al 1 de las personas y sus conversaciones de uno a varios (varios participantes) y experiencias de reuniones. VbSS usa la plataforma de medios (que se basa en UDP como protocolo subyacente), con el objetivo de mejorar las horas de inicio de vídeo, la calidad de visualización de lo que está viendo (especialmente si lo que está viendo es una migración rápida) y la confiabilidad general.
  
Una parte del objetivo de mejorar el uso compartido de la pantalla es que las transiciones entre VbSS y RDP sean tan perfectas como sea posible cuando se produzcan. Dado que VbSS es una actualización de la tecnología subyacente que se usa en la pantalla compartida para Skype empresarial Server, es posible que sea difícil detectar qué tecnología está aprovechando, a menos que esté consultando los detalles del SIP en el tráfico de red o esté compartiendo contenido que se mueve en forma rápida o en 3-D. Si, por ejemplo, el lugar de trabajo tiene una gran cantidad de clientes heredados, RDP seguirá disponible como failsafe para sus reuniones y conversaciones. Skype empresarial Server usa la lógica interna para decidir cuál de los dos métodos (VbSS o uso compartido de pantalla tradicional) debe aplicarse cuando los clientes se conectan. RDP puede sustituirse por VbSS cuando la situación lo reconozca, por lo que la experiencia de visualización no se verá interrumpida.
  
## <a name="planning"></a>Planificación

### <a name="vbss-pros-and-cons"></a>Ventajas y desventajas de VbSS

Cambiar a VbSS pretende hacer tres mejoras clave:
  
1. Crear un uso compartido de pantalla (hasta un 5%) más confiable comparado con RDP solo.

2. Haga que la experiencia de vídeo y la configuración de la sesión sean más rápidas en comparación con RDP solo (Setup en la mitad del tiempo, con una mejora de 6:1 en los fotogramas por segundo).

3. Funciona mucho mejor que RDP en condiciones de ancho de banda bajo, incluso al compartir contenido de alto nivel de movimiento, como gráficos 3D.
    
Tenga en cuenta que estos números confían en el estado y la correcta optimización del rendimiento de la red, y pueden implicar redes externas a su propio equipo, si los clientes están en dispositivos móviles.
  
También debe tener en cuenta que se ha negociado cierta fidelidad o nitidez del contenido compartido en cuanto a fiabilidad, velocidad y eficiencia. En la mayoría de los casos, esto no será fácil de ver para los usuarios.
  
### <a name="ports-and-protocols"></a>Puertos y protocolos

**Puertos de servidor necesarios**

|**Rol del servidor**|**Nombre del servicio**|**Intervalo de puertos o puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de puerto de medios usado para compartir aplicaciones.  <br/> |
   
**Puertos de cliente necesarios**

|**Componente**|**Intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Uso compartido de aplicaciones.  <br/> |
   
Si QoS está habilitada para los siguientes puertos de medios y VbSS también se habilita, durante una conferencia que incluya el uso compartido de escritorio, la MCU usará la configuración del puerto de vídeo que se muestra en negrita a continuación para la pantalla compartir tráfico. 
  
> [!IMPORTANT]
> Estas opciones de configuración son un caso especial y estas opciones precisas deben usarse al implementar ambas características. Esto reemplaza otras opciones recomendadas en la [documentación de QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx). Para el uso compartido de aplicaciones, también deberá especificar ASMCUSVC. exe en el GPO QoS además de definir estos valores de puerto. 
  
**Configuración necesaria de QoS/VbSS del servidor de aplicaciones**

|**Propiedad**|**Valor del puerto**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planeación de capacidad

Cada servidor front-end que ejecute la actualización acumulativa 2 (CU2) de Skype empresarial Server 2015 o posterior admite hasta 375 participantes para el uso compartido de la pantalla con RDP (aunque solo 250 por reunión). Esta capacidad no cambia post-CU3, cuando se presenta y se usa VbSS.
  
Como se dijo, hemos realizado pruebas de rendimiento y estrés en nuestro laboratorio, y también deben tenerse en cuenta las siguientes mediciones con respecto a su propia implementación (en función del uso, por supuesto).
  
Suponiendo
  
- Está usando Skype empresarial Server 2015 CU2 o posterior en su implementación de.
    
- Todos los usuarios de su entorno de Skype empresarial Server tienen resoluciones de pantalla superiores a 1920 x 1080.
    
Con capacidad completa (como se indicó anteriormente) 375 de uso compartido de pantalla de por servidor front-end en total, aunque solo 250 por reunión), es posible que el servidor front-end esté usando un ~ 89% de la tarjeta de red de 1 Gigabit. Esto se debe a que la tecnología de uso compartido de pantalla existente en Skype empresarial Server CU2 (RDP) transmite el contenido en pantalla en la resolución nativa del equipo del moderador. Por lo tanto, con resoluciones de pantalla más altas factorizadas en, es posible que ya haya cuellos de botella de red para el uso compartido de la pantalla con Skype empresarial Server 2015 CU2.
  
Para mitigar esto, puede ser útil una o varias de las siguientes opciones:
  
- Actualice el servidor front-end de una tarjeta de red de 1 Gigabit a una tarjeta Ethernet de 10 Gigabits.

- Aumente el número de servidores front-end para el tráfico de equilibrio de carga.

- Limite el ancho de banda (velocidad de bits) usado para VbSS y RDP colocando un límite en el ancho de banda máximo usado por cualquiera de los canales.
    
Los números de esta tabla se ven influenciados por las redes individuales y por el contenido que se comparte. Realice pruebas para establecer líneas de base para la red o redes.
  
|**Contenido de 1080p**|**Media de RDP**|**Máximo de RDP**|**Valor promedio de VbSS**|**Máximo de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PowerPoint  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3 Mbps  <br/> |2,2 Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia

El ancho de banda de VbSS es:
  
|**Códec de video**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (kbps)**|**Velocidad de bits de carga de vídeo mínima (kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920 x 1080 (16:9)  <br/> (La relación de aspecto depende de la resolución del monitor del compartidor y no siempre será de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Compatibilidad con clientes y servidores

El uso compartido de pantalla basado en vídeo requiere Skype empresarial Server 2015 CU3 o posterior y una versión actual de los clientes compatibles que se enumeran en la [comparación de características de cliente móvil para Skype empresarial](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) y [reuniones compatibles](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Hay situaciones en las que la pantalla compartida se cambiará a RDP, como en el ejemplo siguiente:
  
- Si la cuenta está hospedada en un entorno en el que ASMCU no cumple la compilación mínima compatible con VbSS.
- Si alguien que usa una versión anterior del cliente de Skype empresarial se une a su sesión, por ejemplo cualquier persona que use cualquier versión de cliente de Windows que sea inferior a 16.0.6330.1000, dispositivos de sistema de salas de Skype empresarial o aplicaciones móviles de Skype empresarial. 
- Si un usuario comparte desde la aplicación Web de Skype empresarial.
- Si alguien usa Skype empresarial en Mac y no está hospedado en Skype empresarial online o Skype empresarial Server 2015 con la actualización acumulativa de julio de 2018 (o posterior).
- Si alguien inicia un programa o uso compartido de Windows.
- Si alguien inicia la grabación de la sesión.
- Si alguien invoca el control de pantalla remota durante la sesión. 
- Reuniones con más de 250 participantes (donde VbSS no es compatible actualmente).

Tenga en cuenta que una vez que la sesión pase a RDP, no volverá a VbSS. Una vez más, la transición de VbSS está diseñada para ser transparente y, con la esperanza, no será fácil de detectar en la mayoría de las situaciones.
    
> [!NOTE]
> No se admite bloquear, o intentar bloquear, la transición de VbSS a RDP en el uso compartido de la pantalla de Skype empresarial. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, deshabilitar y configurar VbSS

Lo mejor es que, una vez que haya instalado la actualización acumulativa 3 (CU3) de Skype empresarial Server 2015 o una versión posterior, todos los usuarios se habilitarán de forma predeterminada para la opción 1 a 1 y la de varios participantes. Esto puede resultar problemático si tiene un motivo para no tener esta funcionalidad habilitada para todos los usuarios. En ese caso, puede seguir estos pasos para deshabilitar usuarios (se siguen los pasos de habilitación de los usuarios):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Cómo deshabilitar a los usuarios para que usen VbSS

- Puede asignar una directiva de usuario que no permita VbSS a los usuarios que no deben usar VbSS ejecutando este cmdlet en la consola de administración de Skype empresarial (Reemplace [PolicyName] con la Directiva que está llevando a cabo):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- También puede actualizar la Directiva de conferencia global, que afectará a todos los usuarios sin una directiva asignada:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obtener más información sobre este comando, vea [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si tiene que desactivar por completo VbSS, puede ejecutar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obtener más información sobre este comando, vea [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype for Business con varios participantes, todos los extremos de cliente respetarán la configuración de la Directiva para el organizador de la reunión. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Cómo habilitar a los usuarios para que usen VbSS

- Puede asignar una directiva de usuario específica que permita VbSS a todos los usuarios que necesiten usar VbSS mediante la ejecución de este cmdlet en la consola de administración de Skype empresarial (Reemplace [PolicyName] con la Directiva que está llevando a cabo):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- También puede actualizar la Directiva de conferencia global, que afectará a todos los usuarios sin una directiva asignada:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obtener más información sobre este comando, vea [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita volver a activar VbSS después de desactivarlo (está activado de forma predeterminada), puede ejecutar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obtener más información sobre este comando, vea [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype empresarial de varios participantes, todos los extremos de cliente respetarán la configuración de la Directiva para el organizador de la reunión. 
  
## <a name="see-also"></a>Vea también

[KB3061064 de actualización acumulativa de Skype empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=47690)
  
[El uso compartido de pantalla basado en vídeo (VBSS) está disponible en Skype empresarial Server 2015](https://support.microsoft.com/kb/3170163)
