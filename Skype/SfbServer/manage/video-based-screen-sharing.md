---
title: Pantalla compartida basada en vídeo para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Información de planificación y configuración de Skype empresarial Server para la pantalla compartida basada en vídeo (VbSS)
ms.openlocfilehash: ae2cc683148fdb2a2cb80e3fe3cf25a698a56c00
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548998"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Pantalla compartida basada en vídeo para Skype Empresarial Server 
 
La pantalla compartida basada en vídeo (VbSS) en Skype empresarial Server 2015 ya está disponible para su descarga: [actualización acumulativa de actualización KB3061064 de Skype empresarial server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS se incluye con Skype empresarial Server 2019.
  
La pantalla compartida basada en vídeo, o VbSS, ha extraído el uso compartido de pantalla de Lync. La diferencia entre VbSS y la pantalla compartida tradicional reside en los protocolos subyacentes que se utilizan y en aquello en lo que estos se destacan. La pantalla compartida usa el protocolo de escritorio remoto (RDP), que es excelente para crear miles de sesiones uno a uno entre equipos de diferentes personas. Tecnologías más modernas, como VbSS, harán uso del protocolo de datagramas de usuario (UDP).
  
Skype empresarial Server deseaba mejorar las personas de 1 a 1 y las experiencias de reunión y de 1 a muchos (varios participantes). VbSS hace uso de la plataforma multimedia (que se basa en el UPD como protocolo subyacente), con el objetivo de mejorar las horas de inicio de vídeo, la calidad de visualización de lo que está viendo (especialmente si lo que ve se mueve rápidamente) y la confiabilidad general.
  
Parte del objetivo de mejorar la pantalla compartida es que al producirse transiciones entre VbSS y RDP, estas sean lo más sencillas posible. Como VbSS es una actualización de la tecnología subyacente que se usa en la pantalla compartida para Skype empresarial Server, puede ser difícil detectar qué tecnología se está aprovechando, a menos que se estén consultando los detalles del SIP en el tráfico de red o que se esté compartiendo contenido que es de movimiento rápido o 3D. Si, por ejemplo, su lugar de trabajo tiene una gran cantidad de clientes heredados, RDP seguirá estando disponible como failsafe para sus reuniones y conversaciones. Skype empresarial Server usa la lógica interna para decidir cuál de los dos métodos (VbSS o uso compartido de pantalla tradicional) se aplicará cuando se conecten los clientes. RDP puede sustituirse por VbSS, y de hecho lo hará, cuando la situación lo demande para que la experiencia de visualización no se interrumpa.
  
## <a name="planning"></a>Planeación

### <a name="vbss-pros-and-cons"></a>Pros y contras de VbSS

El cambio a VbSS se produce con el fin de realizar tres mejoras clave:
  
1. Hacer que la pantalla compartida (hasta un 5 %) sea más confiable en comparación con RDP solo.

2. Acelerar la experiencia de vídeo y la configuración de la sesión en comparación con RDP solo (configurar en la mitad del tiempo, con una mejora de 6:1 en los fotogramas por segundo).

3. Funciona mucho mejor que RDP en condiciones de poco ancho de banda, incluso al compartir contenido de alto grado de movimiento, como gráficos 3D.
    
Recuerde que estos números se basan en el ajuste del rendimiento adecuado y el estado de su red, y puede implicar redes externas a la suya si sus clientes están en dispositivos móviles.
  
También debe saber que se ha dejado de lado parte de la fidelidad/precisión del contenido compartido en pos de alcanzar confiabilidad, velocidad y eficiencia. En la mayoría de los casos, esto no será claramente visible para los usuarios.
  
### <a name="ports-and-protocols"></a>Puertos y protocolos

**Puertos de servidor necesarios**

|**Rol de servidor**|**Nombre de servicio**|**Puerto o intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
   
**Puertos de cliente necesarios**

|**Componente**|**Intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Uso compartido de aplicaciones.  <br/> |
   
Si QoS está habilitado para los siguientes puertos multimedia y VbSS también se habilita, durante una conferencia que incluya el uso compartido de escritorio, la MCU AS usará la configuración del puerto de vídeo que se muestra en negrita a continuación para que la pantalla comparta el tráfico. 
  
> [!IMPORTANT]
> Estas opciones de configuración son un caso especial y esta configuración exacta debe usarse al implementar ambas características. Esto reemplaza otra configuración recomendada en la [documentación de QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Para compartir aplicaciones, también tendrá que especificar ASMCUSVC. exe en el GPO QoS además de definir estos valores de puerto. 
  
**Configuración necesaria de QoS/VbSS del servidor de aplicaciones**

|**Propiedad**|**Valor del puerto**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planificación de la capacidad

Cada servidor front-end que ejecute Skype empresarial Server 2015 actualización acumulativa 2 (CU2) o posterior admite hasta 375 participantes para la pantalla compartida con RDP (aunque solo 250 por reunión). Esta capacidad no cambia después de la CU3, cuando se introduce y se utiliza VbSS.
  
Dicho esto, hemos realizado pruebas de esfuerzo y rendimiento en nuestro laboratorio, y también deben tenerse en cuenta las siguientes medidas con respecto a su propia implementación (dependiendo del uso, por supuesto).
  
Supongamos:
  
- Está usando Skype empresarial Server 2015 CU2 o posterior en su implementación.
    
- Todos los usuarios de su entorno de Skype empresarial Server tienen resoluciones de pantalla superiores a 1920 x 1080.
    
Con una capacidad completa (como se indica anteriormente, es 375 participantes de compartir pantalla compartida por cada servidor front-end en total, aunque solo 250 por reunión), es posible que el servidor front-end esté usando ~ 89% de la tarjeta de red de 1 Gigabit. Esto se debe a que la tecnología de uso compartido de pantalla existente en Skype empresarial Server CU2 (RDP) transmite el contenido en pantalla en la resolución nativa del equipo del moderador. Por lo tanto, con las resoluciones de pantalla más altas factorizadas, es posible que ya haya cuellos de botella de red para la pantalla compartida con Skype empresarial Server 2015 CU2.
  
Para mitigar esto, pueden ser útiles una o varias de las siguientes opciones:
  
- Actualiza tu servidor front-end desde una tarjeta de red Gigabit a una tarjeta Ethernet de 10 GB.

- Aumente el número de servidores front-end para equilibrar la carga de tráfico.

- Limite el ancho de banda (velocidad de bits) usado para VbSS y RDP poniendo un tope al ancho de banda máximo utilizado por cualquiera de los canales.
    
Los números en esta tabla se ven influenciados por las redes individuales y por el contenido que se comparte. Intente establecer líneas base para su red o sus redes.
  
|**Contenido de 1080p **|**Promedio de RDP**|**Pico de RDP**|**Promedio de VbSS**|**Pico de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia

El ancho de banda de VbSS es:
  
|**Códec de vídeo**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (Kbps)**|**Velocidad de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x 1080 (16:9)  <br/> (La relación de aspecto depende de la resolución del monitor de quien comparte, y no será siempre de 16:9).  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Compatibilidad con clientes y servidores

La pantalla compartida basada en vídeo requiere Skype empresarial Server 2015 CU3 o posterior, y una versión actual de los clientes de soporte que se incluyen en la [comparación de características de cliente móvil para](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) la [compatibilidad con reuniones](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)y Skype empresarial. 
  
Hay situaciones en las que la pantalla compartida se cambiará a RDP, como se muestra a continuación:
  
- Si la cuenta está alojada en un entorno en el que ASMCU no cumple con la compilación mínima admitida por VbSS.
- Si alguien que usa una versión anterior del cliente de Skype empresarial se une a su sesión, por ejemplo, cualquier persona que use cualquier versión de cliente de Windows que sea anterior a 16.0.6330.1000, dispositivos de sistema de la sala de Skype para empresas o aplicaciones móviles de Skype empresarial. 
- Si un usuario comparte desde la aplicación Web de Skype empresarial.
- Si alguien está usando Skype empresarial en Mac y no está alojado en Skype empresarial online o en Skype empresarial Server 2015, con la actualización acumulativa de julio de 2018 (o una versión posterior).
- Si alguien inicia un programa o uso compartido de Windows.
- Si alguien comienza a grabar la sesión.
- Si alguien invoca al control de pantalla remota durante la sesión. 
- En el caso de reuniones con más de 250 participantes (donde VbSS no es compatible actualmente).

Tenga en cuenta que cuando la sesión cambie a RDP, no volverá a VbSS. Nuevamente, la transición de VbSS debe ser ininterrumpida y, es de esperar, que no sea sencillo detectarla en la mayoría de los casos.
    
> [!NOTE]
> No es posible bloquear o intentar bloquear la transición de VbSS a RDP en el uso compartido de pantalla en Skype empresarial. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, deshabilitar y configurar VbSS

Lo mejor es que, una vez que haya instalado la actualización acumulativa 3 (CU3) de Skype empresarial Server 2015 o una versión posterior, todos los usuarios estarán habilitados para 1 a 1 y para varias partes VbSS de forma predeterminada. Esto puede resultar problemático si, por alguna causa, no tiene esta funcionalidad habilitada para todos los usuarios. En ese caso, puede seguir los pasos que se indican a continuación para deshabilitar usuarios (después se ofrecen los pasos para habilitarlos):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Cómo deshabilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva de usuario que no permita VbSS a los usuarios que no deberían usar VbSS ejecutando este cmdlet en la consola de administración de Skype empresarial (Reemplace [PolicyName] por la Directiva que está haciendo):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obtener más información sobre este comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita desactivar VbSS por completo, puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obtener más información sobre este comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype empresarial entre varias empresas, todos los puntos de conexión de cliente respetarán la configuración de directiva del organizador de la reunión. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Cómo habilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva de usuario específica que permita VbSS a todos los usuarios que necesiten usar VbSS ejecutando este cmdlet en la consola de administración de Skype empresarial (Reemplace [PolicyName] por la Directiva que está haciendo):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obtener más información sobre este comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita volver a activar VbSS después de desactivarla (está activada de manera predeterminada), puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obtener más información sobre este comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una reunión de Skype empresarial de varios participantes, todos los puntos de conexión de cliente respetarán la configuración de directiva para el organizador de la reunión. 
  
## <a name="see-also"></a>Vea también

[Paquete de actualización acumulativa 2015 de Skype empresarial KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[El uso compartido de pantalla basado en vídeo (VBSS) está disponible en Skype empresarial Server 2015](https://support.microsoft.com/en-us/kb/3170163)
