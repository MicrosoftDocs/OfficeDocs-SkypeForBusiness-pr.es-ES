---
title: Vídeo según el uso compartido de la pantalla de Skype para Business Server
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype para obtener información de planeación y configuración de Business Server para vídeo compartida basado en pantalla (VbSS)
ms.openlocfilehash: a658453af5f71d7bb8103411ed16c534e3004a03
ms.sourcegitcommit: aa3258aeb5aa1296c4bb251a9d258b8896457b7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "23935478"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Vídeo según el uso compartido de la pantalla de Skype para Business Server 
 
Vídeo compartida basado en pantalla (VbSS) en Skype para Business Server 2015 está ahora disponible para su descarga: [Skype para KB3061064 de actualización acumulativa de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS se incluye con Skype para Business Server 2019.
  
Vídeo basadas en el uso compartido de la pantalla o VbSS, dejó de usar Lync uso compartido de pantalla. La diferencia entre VbSS y la pantalla compartida tradicional reside en los protocolos subyacentes que se utilizan y en aquello en lo que estos se destacan. La pantalla compartida usa el protocolo de escritorio remoto (RDP), que es excelente para crear miles de sesiones uno a uno entre equipos de diferentes personas. Tecnologías más modernas, como VbSS, harán uso del protocolo de datagramas de usuario (UDP).
  
Skype para Business Server deseaba mejorar de 1 a 1 de las personas y sus conversaciones (varios participantes) de 1 a muchos y experiencias de la reunión. VbSS hace uso de la plataforma multimedia (que se basa en el UPD como protocolo subyacente), con el objetivo de mejorar las horas de inicio de vídeo, la calidad de visualización de lo que está viendo (especialmente si lo que ve se mueve rápidamente) y la confiabilidad general.
  
Parte del objetivo de mejorar la pantalla compartida es que al producirse transiciones entre VbSS y RDP, estas sean lo más sencillas posible. Puesto que VbSS es una actualización de la tecnología subyacente que se usa en la pantalla de uso compartido de Skype para Business Server, puede ser difícil detectar qué tecnología está aprovechando a menos que está viendo los detalles SIP en el tráfico de red, o que está compartiendo contenido que es mover fast o 3D. Si, por ejemplo, el área de trabajo tiene una gran cantidad de los clientes heredados, RDP aún estará disponible como un a prueba de errores para sus reuniones y conversaciones. Skype para Business Server usa la lógica interna para decidir cuál de los dos métodos (VbSS o tradicional de uso compartido pantalla) que se debe aplicar cuando los clientes se conectan. RDP puede sustituirse por VbSS, y de hecho lo hará, cuando la situación lo demande para que la experiencia de visualización no se interrumpa.
  
## <a name="planning"></a>Planeación

### <a name="vbss-pros-and-cons"></a>Pros y contras de VbSS

El cambio a VbSS se produce con el fin de realizar tres mejoras clave:
  
1. Hacer que la pantalla compartida (hasta un 5 %) sea más confiable en comparación con RDP solo.

2. Acelerar la experiencia de vídeo y la configuración de la sesión en comparación con RDP solo (configurar en la mitad del tiempo, con una mejora de 6:1 en los fotogramas por segundo).

3. Funciona mucho mejor que RDP en condiciones de poco ancho de banda, incluso al compartir contenido de alto grado de movimiento, como gráficos 3D.
    
Recuerde que estos números se basan en el ajuste del rendimiento adecuado y el estado de su red, y puede implicar redes externas a la suya si sus clientes están en dispositivos móviles.
  
También debe saber que se ha dejado de lado parte de la fidelidad/precisión del contenido compartido en pos de alcanzar confiabilidad, velocidad y eficiencia. En la mayoría de los casos, esto no será claramente visible para los usuarios.
  
### <a name="ports-and-protocols"></a>Puertos y protocolos

**Puertos de servidor necesarias**

|**Rol de servidor**|**Nombre de servicio**|**Puerto o intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
   
**Puertos de cliente requerida**

|**Componente**|**Intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Uso compartido de aplicaciones.  <br/> |
   
Si QoS está habilitado para los siguientes puertos de medios y VbSS también está habilitada, durante una conferencia que incluye el uso compartido de escritorio en que la MCU AS usará la configuración de puertos de vídeo que se muestra negrita a continuación para el tráfico de recurso compartido de la pantalla. 
  
> [!IMPORTANT]
> Estos valores se encuentran un caso especial y se debe usar esta configuración exacta al implementar ambas de estas características. Esto reemplaza otra configuración recomendada en la [documentación de QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). También tendrá que especificar ASMCUSVC.exe en el GPO de QoS además de definir estos valores de puerto el uso compartido de aplicaciones de fo. 
  
**Servidor de aplicación de QoS/VbSS la configuración necesaria**

|**Propiedad**|**Valor de puerto**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>Planificación de la capacidad

Cada servidor Front-End que ejecuta Skype para Business Server 2015 actualización acumulativa 2 (CU2) o posterior es compatible con los participantes hasta 375 para pantalla uso compartido mediante RDP (aunque sólo 250 por reunión). Esta capacidad no cambia después de la CU3, cuando se introduce y se utiliza VbSS.
  
Dicho esto, hemos realizado pruebas de esfuerzo y rendimiento en nuestro laboratorio, y también deben tenerse en cuenta las siguientes medidas con respecto a su propia implementación (dependiendo del uso, por supuesto).
  
Supongamos:
  
- Usa Skype para Business Server 2015 CU2 o más adelante en la implementación.
    
- Todos los usuarios de su Skype para entorno Business Server tienen resoluciones de pantalla superiores a 1920 x 1080.
    
Con plena capacidad (que tal y como se mencionó anteriormente, es 375 participantes de uso compartido de pantalla por servidor Front-End en total, aunque sólo 250 por reunión), el servidor Front-End pueden estar utilizando ~ 89% de la 1 Gigabit de tarjeta de red. Esto es debido a que la pantalla existente de uso compartido de la tecnología de Skype para Business Server CU2 (RDP) transmite el contenido en pantalla en la resolución nativa del PC del moderador. Por lo tanto con resolución de pantalla alta factorizada, puede ya estar experimentando cuellos de botella de red para compartir con Skype para Business Server 2015 CU2 de pantalla.
  
Para mitigar esto, pueden ser útiles una o varias de las siguientes opciones:
  
- Actualizar el servidor Front-End desde una tarjeta de red 1 Gigabit a una tarjeta Gigabit Ethernet 10.

- Aumentar el número de servidores Front-End para el tráfico de equilibrio de carga.

- Limite el ancho de banda (velocidad de bits) usado para VbSS y RDP poniendo un tope al ancho de banda máximo utilizado por cualquiera de los canales.
    
Los números en esta tabla se ven influenciados por las redes individuales y por el contenido que se comparte. Intente establecer líneas base para su red o sus redes.
  
|**Contenido de 1080p **|**Promedio RDP**|**Pico de RDP**|**Promedio de VbSS**|**Pico de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12 Mbps  <br/> |100kbps  <br/> |3 Mbps  <br/> |
|CAD  <br/> |3 Mbps  <br/> |7mbps  <br/> |1 Mbps  <br/> |3 Mbps  <br/> |
|Vídeo  <br/> |5 Mbps  <br/> |7mbps  <br/> |1.3Mbps  <br/> |2.2Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia

El ancho de banda de VbSS es:
  
|**Códec de vídeo**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (Kbps)**|**Velocidad de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x 1080 (16:9)  <br/> (La relación de aspecto depende de la resolución del monitor de quien comparte, y no será siempre de 16:9).  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Compatibilidad con clientes y servidores

En función de vídeo el uso compartido de pantalla requiere Skype para Business Server 2015 CU3 o posterior y una versión actual de los clientes auxiliares que aparecen en la [comparación de características de cliente móvil de Skype para la empresa](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) y [soporte técnico de las reuniones](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Hay situaciones donde uso compartido de pantalla va a realizar la transición a RDP, como las siguientes:
  
- Si la cuenta está alojada en un entorno en el que ASMCU no cumple con la compilación mínima admitida por VbSS.
- Si una persona que usa una versión anterior de la Skype para clientes empresariales se une a la sesión, por ejemplo cualquier persona con cualquier versión de cliente de Windows que es menor que 16.0.6330.1000, Skype para dispositivos del sistema empresarial salón o Skype para aplicaciones empresariales de Mobile. 
- Si un usuario está compartiendo desde el Skype para la aplicación empresarial de Web.
- Si alguien usa Skype para la empresa en Mac y no está hospedado en Skype para profesionales en línea.
- Si alguien inicia cualquier programa o Windows uso compartido.
- Si alguien inicia la grabación de la sesión.
- Si alguien invoca al control de pantalla remota durante la sesión.

    Tenga en cuenta que cuando la sesión cambie a RDP, no volverá a VbSS. Nuevamente, la transición de VbSS debe ser ininterrumpida y, es de esperar, que no sea sencillo detectarla en la mayoría de los casos.
  
- En el caso de reuniones con más de 250 participantes (donde VbSS no es compatible actualmente).
    
> [!NOTE]
> No se admite el bloque, o intenta bloquear, la transición de VbSS a RDP en Skype para compartir la pantalla empresarial. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, deshabilitar y configurar VbSS

Lo mejor es que, una vez que ha instalado el Skype para Business Server 2015 actualización acumulativa 3 (CU3) o posterior, se habilitará todos los usuarios para VbSS 1-1 y varios participantes de forma predeterminada. Esto puede resultar problemático si, por alguna causa, no tiene esta funcionalidad habilitada para todos los usuarios. En ese caso, puede seguir los pasos que se indican a continuación para deshabilitar usuarios (después se ofrecen los pasos para habilitarlos):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Cómo deshabilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva de usuario que no permite VbSS a los usuarios que no deberían utilizar VbSS mediante la ejecución de este cmdlet en el Skype para consola de administración empresarial (reemplazar [PolicyName] con la directiva que está haciendo para):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obtener más información acerca de este comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita desactivar VbSS por completo, puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obtener más información sobre este comando, vea [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En un Skype con varios participantes de la reunión de negocios, todos los extremos de cliente va a respetar la configuración de directiva para el organizador de la reunión. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Cómo habilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva de usuario específico que permita VbSS a todos los usuarios que necesiten usar VbSS mediante la ejecución de este cmdlet en el Skype para consola de administración empresarial (reemplazar [PolicyName] con la directiva que está haciendo para):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obtener más información acerca de este comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita volver a activar VbSS después de desactivarla (está activada de manera predeterminada), puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obtener más información sobre este comando, vea [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En un Skype varios participantes de la reunión de negocios, todos los extremos de cliente va a respetar la configuración de directiva para el organizador de la reunión. 
  
## <a name="see-also"></a>Vea también

[Skype para Business Server 2015 actualización acumulativa KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[En función de vídeo pantalla uso compartido (VBSS) está disponible en Skype para Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)
