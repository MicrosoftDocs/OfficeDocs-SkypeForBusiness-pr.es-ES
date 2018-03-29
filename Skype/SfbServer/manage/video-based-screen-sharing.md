---
title: Pantalla compartida basada en vídeo para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 'Skype para obtener información de planificación y configuración de Business Server 2015 para vídeo pantalla compartida (VbSS), que ahora está disponible para su descarga: Skype para KB3061064 de actualización acumulativa de Business Server 2015.'
ms.openlocfilehash: 21b7868efb9b1a6621aa85cae277114629d67551
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a>Pantalla compartida basada en vídeo para Skype Empresarial Server 2015
 
Skype para obtener información de planificación y configuración de Business Server 2015 para vídeo pantalla compartida (VbSS), que ahora está disponible para su descarga: [Skype para KB3061064 de actualización acumulativa de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690).
  
Vídeo basado en el uso compartido de la pantalla, o VbSS, surgió de Lync el uso compartido de pantalla. La diferencia entre VbSS y la pantalla compartida tradicional reside en los protocolos subyacentes que se utilizan y en aquello en lo que estos se destacan. La pantalla compartida usa el protocolo de escritorio remoto (RDP), que es excelente para crear miles de sesiones uno a uno entre equipos de diferentes personas. Tecnologías más modernas, como VbSS, harán uso del protocolo de datagramas de usuario (UDP).
  
Skype para Business Server deseaba mejorar 1 a 1 popular y sus conversaciones (varias partes) 1-a-muchos y experiencias de la reunión. VbSS hace uso de la plataforma multimedia (que se basa en el UPD como protocolo subyacente), con el objetivo de mejorar las horas de inicio de vídeo, la calidad de visualización de lo que está viendo (especialmente si lo que ve se mueve rápidamente) y la confiabilidad general.
  
Parte del objetivo de mejorar la pantalla compartida es que al producirse transiciones entre VbSS y RDP, estas sean lo más sencillas posible. Como VbSS es una actualización de la tecnología subyacente que se utiliza en pantalla compartida de Skype para Business Server, puede ser difícil de detectar qué tecnología están aprovechando a menos que está viendo los detalles SIP en el tráfico de red o comparte el contenido que es rápida evolución o 3D. Si, por ejemplo, su lugar de trabajo tiene un montón de clientes heredados, RDP todavía estará disponible como infalible para sus reuniones y conversaciones. Skype para Business Server usa la lógica interna para decidir cuál de los dos métodos (VbSS o compartir tradicional de pantalla) para aplicar cuando los clientes se conectan. RDP puede sustituirse por VbSS, y de hecho lo hará, cuando la situación lo demande para que la experiencia de visualización no se interrumpa.
  
## <a name="planning"></a>Planeación

### <a name="vbss-pros-and-cons"></a>Pros y contras de VbSS

El cambio a VbSS se produce con el fin de realizar tres mejoras clave:
  
1. Hacer que la pantalla compartida (hasta un 5 %) sea más confiable en comparación con RDP solo.

2. Acelerar la experiencia de vídeo y la configuración de la sesión en comparación con RDP solo (configurar en la mitad del tiempo, con una mejora de 6:1 en los fotogramas por segundo).

3. Funciona mucho mejor que RDP en condiciones de poco ancho de banda, incluso al compartir contenido de alto grado de movimiento, como gráficos 3D.
    
Recuerde que estos números se basan en el ajuste del rendimiento adecuado y el estado de su red, y puede implicar redes externas a la suya si sus clientes están en dispositivos móviles.
  
También debe saber que se ha dejado de lado parte de la fidelidad/precisión del contenido compartido en pos de alcanzar confiabilidad, velocidad y eficiencia. En la mayoría de los casos, esto no será claramente visible para los usuarios.
  
### <a name="ports-and-protocols"></a>Puertos y protocolos

**Puertos de servidor requerido**

|**Función de servidor**|**Nombre de servicio**|**Puerto o rango**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
   
**Puertos de cliente requerido**

|**Componente**|**Intervalo de puertos**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Uso compartido de aplicaciones.  <br/> |
   
Si QoS está habilitado para los siguientes puertos de medios y VbSS también está habilitada, durante una conferencia que incluye el uso compartido de escritorio en que la MCU AS utilizará la configuración de puerto de vídeo que se muestra negrita a continuación para el tráfico de recurso compartido de la pantalla. 
  
> [!IMPORTANT]
> Estos valores son un caso especial, y estos valores exactos que deben utilizarse al implementar ambas características. Esto reemplaza otras configuraciones recomendadas en la [documentación de QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Aplicación de fo compartida también deberá especificar ASMCUSVC.exe en el GPO de QoS, además de definir estos valores de puerto. 
  
**Configuración de servidor de aplicación QoS/VbSS necesaria**

|**Propiedad**|**Valor del puerto**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>Planificación de la capacidad

Cada servidor Front-End que ejecuta Skype para Business Server 2015 actualización acumulativa 2 (CU2) admite a hasta 375 participantes para pantalla compartida con RDP (aunque sólo 250 por reunión). Esta capacidad no cambia después de la CU3, cuando se introduce y se utiliza VbSS.
  
Dicho esto, hemos realizado pruebas de esfuerzo y rendimiento en nuestro laboratorio, y también deben tenerse en cuenta las siguientes medidas con respecto a su propia implementación (dependiendo del uso, por supuesto).
  
Supongamos:
  
- Utiliza Skype para Business Server 2015 CU2 en su implementación.
    
- Todos los usuarios de su Skype para entorno Business Server tienen resoluciones de pantalla superiores a 1920 x 1080.
    
A plena capacidad (que como se mencionó anteriormente, es 375 participantes de uso compartido de pantalla por cada servidor Front-End en total, aunque sólo 250 por reunión), el servidor Front-End pueden estar utilizando ~ 89% de lo 1 Gigabit de la tarjeta de red. Esto es porque la pantalla existente compartir tecnología en Skype para Business Server CU2 (RDP) transmite el contenido en pantalla a la resolución nativa del equipo del moderador. Por lo que con la resolución de pantalla alta tenidos en cuenta, puede ya estar experimentando cuellos de botella de red para compartir con Skype para Business Server 2015 CU2 de pantalla.
  
Para mitigar esto, pueden ser útiles una o varias de las siguientes opciones:
  
- Actualizar el servidor Front-End de una tarjeta de red Gigabit 1 a una tarjeta Ethernet Gigabit 10.

- Aumentar el número de servidores frontales de tráfico de equilibrio de carga.

- Limite el ancho de banda (velocidad de bits) usado para VbSS y RDP poniendo un tope al ancho de banda máximo utilizado por cualquiera de los canales.
    
Los números en esta tabla se ven influenciados por las redes individuales y por el contenido que se comparte. Intente establecer líneas base para su red o sus redes.
  
|**Contenido de 1080p**|**Promedio RPD**|**Pico de RDP**|**Promedio de VbSS**|**Pico de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12 Mbps  <br/> |100kbps  <br/> |3 Mbps  <br/> |
|CAD  <br/> |3 Mbps  <br/> |7mbps  <br/> |1 Mbps  <br/> |3 Mbps  <br/> |
|Vídeo  <br/> |5 Mbps  <br/> |7mbps  <br/> |1.3Mbps  <br/> |2.2Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia

El ancho de banda de VbSS es:
  
|**Códec de vídeo**|**Resolución y relación de aspecto**|**Velocidad de bits de vídeo máxima de la carga (Kbps)**|**Carga de vídeo mínima velocidad de bits (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x 1080 (16:9)  <br/> (La relación de aspecto depende de la resolución del monitor de quien comparte, y no será siempre de 16:9).  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Compatibilidad con clientes y servidores

Vídeo pantalla compartida requiere Skype para Business Server 2015 CU3 o posterior y una versión actual de clientes compatibles enumerados en la [comparación de características de cliente móvil de Skype para el negocio](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) y [soporte de las reuniones](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Existen situaciones donde compartir pantalla pasará a RDP, como estos:
  
- Si la cuenta está alojada en un entorno en el que ASMCU no cumple con la compilación mínima admitida por VbSS.
- Si una persona que utiliza una versión anterior de la Skype para Business client une a la sesión, por ejemplo cualquiera utilizando cualquier versión de cliente de Windows que es menor que 16.0.6330.1000, Skype para dispositivos de sistema de sala de negocio o Skype para aplicaciones móviles de negocio. 
- Si un usuario comparte desde el Skype para el negocio de la aplicación Web.
- Si alguien utiliza Skype para Businesson Mac y no se encuentra alojado en Skype para los negocios en línea.
- Si alguien inicia un programa o recurso compartido de Windows, o una grabación durante la sesión.
- Si alguien invoca al control de pantalla remota durante la sesión.

    Tenga en cuenta que cuando la sesión cambie a RDP, no volverá a VbSS. Nuevamente, la transición de VbSS debe ser ininterrumpida y, es de esperar, que no sea sencillo detectarla en la mayoría de los casos.
  
- En el caso de reuniones con más de 250 participantes (donde VbSS no es compatible actualmente).
    
> [!NOTE]
> No se admite el bloque, o intentar bloquear, transición de VbSS a RDP en Skype para compartir la pantalla de negocios. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, deshabilitar y configurar VbSS

Lo mejor es que, una vez que haya instalado el Skype para Business Server 2015 actualización acumulativa 3 (CU3), todos los usuarios se habilitará para VbSS de 1 a 1 y con varios usuarios de forma predeterminada. Esto puede resultar problemático si, por alguna causa, no tiene esta funcionalidad habilitada para todos los usuarios. En ese caso, puede seguir los pasos que se indican a continuación para deshabilitar usuarios (después se ofrecen los pasos para habilitarlos):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Cómo deshabilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva de usuario que no permite VbSS a los usuarios que no deberían utilizar VbSS al ejecutar este cmdlet en el Skype para consola de administración de negocios (reemplazar [PolicyName] con la directiva que está haciendo para):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obtener más información sobre este comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita desactivar VbSS por completo, puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obtener más información sobre este comando, consulte [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En un Skype con varios participantes de la reunión de negocios, todos los extremos de cliente respetará la configuración de directiva para el organizador de la reunión. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Cómo habilitar la utilización de VbSS por parte de los usuarios

- Puede asignar una directiva específica del usuario que permite a los usuarios que deben utilizar VbSS al ejecutar este cmdlet en el Skype para consola de administración de negocios (reemplazar [PolicyName] con la directiva que está haciendo para) VbSS:
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- También puede actualizar la directiva de conferencia global, que afectará a todos los usuarios que no tengan una directiva asignada:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obtener más información sobre este comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si necesita volver a activar VbSS después de desactivarla (está activada de manera predeterminada), puede ejecutar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obtener más información sobre este comando, consulte [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> En una multiconferencia Skype para reuniones de negocios, todos los extremos de cliente respetará la configuración de directiva para el organizador de la reunión. 
  
## <a name="see-also"></a>Vea también

#### 

[Skype para Business Server 2015 actualización acumulativa KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[En vídeo compartida pantalla (VBSS) está disponible en Skype para Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)

