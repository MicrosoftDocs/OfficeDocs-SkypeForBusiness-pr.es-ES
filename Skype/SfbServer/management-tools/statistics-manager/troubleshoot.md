---
title: Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumen: Lea este tema para solucionar problemas de la implementación del Administrador de estadísticas de Skype para Business Server.'
ms.openlocfilehash: dbdf536b43006f5619330e93de0b8aba5024a1ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906686"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
 
**Resumen:** Lea este tema para solucionar problemas de la implementación del Administrador de estadísticas de Skype para Business Server.
  
En este tema se describe cómo solucionar problemas de la implementación del Administrador de estadísticas mediante la descripción de eventos, es posible que vea en el registro de eventos de aplicación y las acciones adecuadas que puede tardar para corregir el evento. Este tema contiene las siguientes secciones:
  
- [Eventos del agente](troubleshoot.md#BKMK_Agent)
    
- [Eventos de escucha](troubleshoot.md#BKMK_Listener)
    
- [Problemas de sitio web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventos del agente
<a name="BKMK_Agent"> </a>

- **1000**: no se puede configurar el limitador de procesador (objeto de trabajo). Motivo desconocido
    
- **1001** : limitar el proceso no se permite en el proceso (probablemente ya dentro de un objeto de trabajo)
    
    El agente se ejecuta en un objeto de trabajo de Windows para limitar automáticamente su superficie de memoria. Si el agente no se inicia y estas entradas de evento se encuentran en el registro de eventos, no se puede crear una instancia del objeto de trabajo en el servidor. Para evitar este problema, se puede quitar el límite de memoria superior cambiando un valor en el archivo de configuración:
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Buscar "MaxProcessMemoryMB" y cambie el valor a "0" como se muestra:
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si se realiza este cambio, el agente sigue generalmente consumirá \< 100 MB de memoria, sin embargo no será forzosamente limitado a 300 MB como es el valor predeterminado. Si se realiza este cambio, se recomienda estrechamente supervisar el uso de memoria para garantizar al agente no consumir una gran cantidad de memoria en el equipo host. 
  
- **2000**: error en la inicialización del cliente
    
- **2001**: no se pudo establecer ninguna conexión con el servicio ni con ninguna IP de origen
    
    Si el agente no puede conectarse con el equipo de escucha, compruebe lo siguiente:
    
1. Garantice que el servicio de escucha se esté ejecutando en el equipo de escucha. Si no, asegúrese de que Redis se esté ejecutando en ese servidor y, a continuación, reinicie el servicio de escucha.
    
    Compruebe el registro de eventos de estadísticas administrador en el equipo de agente de escucha para no asegurarse de que no haya ningún problema con el propio servicio de agente de escucha de las estadísticas de administrador.
    
2. Use una herramienta de conectividad como telnet para comprobar la conectividad desde el equipo del agente al de escucha en el puerto correcto.
    
    Si no, asegúrese de que la regla de firewall entrante esté habilitada en el equipo de escucha para el tipo de red al que está conectado el equipo de escucha (privado/público/dominio). Si el equipo de agente de escucha no está unido a un dominio, la red puede aparecer como pública y en ese caso no se aplicarán las reglas de firewall que se instalan con el Administrador de estadísticas de forma predeterminada.
    
- **4000**: error al descargar información del servidor desde la escucha (motivo desconocido)
    
  - **4001**: no se encuentra el servidor en la topología de escucha
    
    Se producirá este error si el servidor se conecta correctamente al agente de escucha, pero el servidor no se ha agregado a la topología en memoria caché del agente de escucha. Opciones de resolución:
    
  - 	Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología](deploy.md#BKMK_ImportTopology).   
    
  - Si el agente está en un servidor que no se incluye en la topología (por ejemplo, los nodos de un clúster SQL AlwaysOn), tendrá que agregar el agente manualmente siguiendo las instrucciones de [Importar la topología](deploy.md#BKMK_ImportTopology).
    
  - **4002**: contraseña de escucha no válida
    
    La contraseña cifrada que el agente intenta usar no coincide con la contraseña de servicio de la escucha. Desinstale el agente y vuelva a instalarlo con la contraseña de servicio correcta.
    
  - **4003**: la huella digital del certificado no coincide
    
    La huella digital del certificado proporcionado al agente durante la instalación no coincide con la huella digital en el certificado que la escucha está usando actualmente y, por lo tanto, la conexión se rechazará. Desinstale el agente y vuelva a instalarlo con la huella digital del certificado correcta.
    
  - **4004**: respuesta no válida o HttpStatusCode
    
    La escucha no responde con un estado esperado.   
    
  - Si la conexión se realiza mediante proxy, compruebe la configuración de proxy.
    
  - Comprobar el registro de StatsMan del equipo de agente de escucha para problemas con su configuración.
    
  - **4005**: no se pudo deserializar el XML
    
    La información del servidor en el servidor de escucha está dañada o puede que haya un conflicto de versiones entre el agente y los equipos de escucha. Asegúrese de que las versiones coincidan y compruebe si hay problemas en el registro de eventos de la escucha.
    
## <a name="listener-events"></a>Eventos de escucha
<a name="BKMK_Listener"> </a>

- **10000**: error de inicio con motivo desconocido (son irrecuperables y, como resultado, el servicio se detendrá/bloqueará)
    
  - **10001**: problema de configuración
    
    En general, se produce cuando el archivo [listener_install_location]\PerfAgentListener.exe.config se ha modificado manualmente y la aplicación no puede leerlo.
    
  - **10002**: error de inicialización de la escucha HTTP
    
    Por lo general, este evento se registra cuando la ACL de dirección URL no se ha configurado correctamente durante la instalación o el certificado SSL no es válido. Asegúrese de que el certificado de su configuración sea válido. Si lo es, reinstale la escucha según las instrucciones de [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).
    
  - **10003**: error de Redis
    
  - **10004**: error de almacenamiento en caché de la infraestructura
    
  - **10007**: configuración (almacenada en redis)
    
    La escucha no pudo establecer contacto con Redis o recuperar datos bien formados de la caché y no se pudo iniciar. Asegúrese de que el servicio Redis se haya iniciado y configurado correctamente en el servidor.
    
  - **10005**: recuperación/análisis de la información del servidor
    
    La información de topología en la caché de Redis no es válida. Primero, intente reiniciar Redis y la escucha. Si el error persiste, consulte [Importar la topología](deploy.md#BKMK_ImportTopology) para volver a crear los datos de la topología.
    
- **10100**: interrupción del PING de Redis
    
  - **10101**: interrupción continuada del PING de Redis (cada 60 segundos)
    
  - **30100**: interrupción del PING de Redis restaurada
    
    Estos eventos se registran cuando la escucha no puede conectarse a Redis. Asegúrese de que Redis se haya iniciado y de que la conectividad de red entre la escucha y Redis esté disponible.
    
- **10200**: interrupción de la escritura de Redis
    
  - **10201**: interrupción continuada de la escritura de Redis (cada 60 segundos)
    
  - **30100**: interrupción de la escritura de Redis resuelta
    
    Estos eventos se registran cuando la escucha no puede escribir en la caché de Redis. Asegúrese de que Redis se haya iniciado y de que la conectividad entre la escucha y Redis esté disponible.
    
- **30000**: se ha iniciado correctamente
    
    Se registra cada vez que se inicia la escucha.
    
- **22000** : inicialización del Administrador de estadísticas de agente se ha realizado correctamente.
    
- **23000**: EventLogQueryManager se ha inicializado correctamente (primera vez o después de un error)
    
- **24000**: la información del servidor se ha inicializado correctamente (primera vez o después de un error)
    
- **25000**: la escucha vuelve a estar en línea después de un error al publicar (o primera publicación realizada correctamente)
    
- **5000**: inicio de la escucha sin conexión para publicar datos
    
- **5001**: la escucha todavía está sin conexión durante un período de tiempo prolongado
    
    Estos eventos pueden ser útiles para supervisar o comprender problemas o alertar de ellos.
    
## <a name="website-issues"></a>Problemas de sitio web
<a name="BKMK_Website"> </a>

- Inicio de sesión repetitiva solicita en cromo - era un error que se ha resuelto en la versión 1.1. Asegúrese de que haber actualizado a la versión más reciente del Administrador de estadísticas si está viendo solicitudes de inicio de sesión repetidas en el Explorador de cromo. Para comprobar la versión del sitio web en el que se está ejecutando:
    
  - 	En el Explorador de archivos, abra (directorio predeterminado)
    
  - Haga clic con el botón derecho en StatsManHubWebSite.dll y consulte sus propiedades.
    
  - Si un equipo no se encuentra en la vista horizontal de KHI o en la vista Detalles de contador, asegúrese de que sea miembro de un sitio y un grupo. Si no lo es, no aparecerá en esas vistas. Para obtener información sobre cómo definir un sitio y un grupo para un servidor en la topología, vea [Importar la topología](deploy.md#BKMK_ImportTopology).
    
  - La versión del producto se mostrará en los detalles de Descripción.
    
## <a name="for-more-information"></a>Más información
<a name="BKMK_Website"> </a>

Para obtener más información, vea los artículos siguientes:
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)
    
- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)
