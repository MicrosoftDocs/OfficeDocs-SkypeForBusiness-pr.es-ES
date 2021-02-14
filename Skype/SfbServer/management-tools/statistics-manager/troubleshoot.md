---
title: Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumen: lea este tema para solucionar problemas de implementación del Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821780"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
 
**Resumen:** Lea este tema para solucionar problemas de implementación del Administrador de estadísticas para Skype Empresarial Server.
  
En este tema se describe cómo solucionar problemas de la implementación del Administrador de estadísticas mediante la descripción de los eventos que puede ver en el registro de eventos de la aplicación y las acciones apropiadas que puede realizar para corregir el evento. En este tema se presentan las siguientes secciones:
  
- [Eventos de agente](troubleshoot.md#BKMK_Agent)
    
- [Eventos de escucha](troubleshoot.md#BKMK_Listener)
    
- [Problemas del sitio web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventos de agente
<a name="BKMK_Agent"> </a>

- **1000** — No se puede configurar el limitador de procesador (objeto job): motivo desconocido
    
- **1001:** No se permite la limitación de procesos en el proceso (probablemente ya dentro de un objeto Job)
    
    El agente se ejecuta dentro de un objeto de trabajo de Windows para limitar automáticamente su superficie de memoria. Si el agente no se iniciará y estas entradas de evento están presentes en el registro de eventos, no se podrá crear una instancia del objeto job en el servidor. Para evitar esto, se puede quitar el límite de memoria superior cambiando un valor en el archivo de configuración:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Busque "MaxProcessMemoryMB" y cambie el valor a "0", como se muestra:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si se realiza este cambio, el agente generalmente seguirá consumiendo 100 MB de memoria, pero no se limitará a la fuerza a 300 MB como es el valor \< predeterminado. Si se realiza este cambio, se recomienda supervisar estrechamente el uso de memoria para asegurarse de que el agente no consume una gran cantidad de memoria en su equipo host. 
  
- **2000:** Error de inicialización del cliente
    
- **2001:** No se pudo realizar ninguna conexión con el servicio en ninguna IP de origen
    
    Si el agente no puede conectarse al equipo de escucha, compruebe lo siguiente:
    
    1. Asegúrese de que el servicio de escucha se está ejecutando en el equipo de escucha. Si no es así, asegúrese de que Redis se ejecuta en ese servidor y, a continuación, reinicie el servicio de escucha.
        
        Compruebe el registro de eventos del Administrador de estadísticas en el equipo de escucha para asegurarse de que no hay problemas con el servicio de escucha del administrador de estadísticas en sí.
        
    2. Use una herramienta de conectividad como telnet para comprobar la conectividad desde el equipo del agente al servicio de escucha en el puerto correcto.
        
        Si no es así, asegúrese de que la regla de firewall entrante está habilitada en el equipo de escucha para el tipo de red al que está conectado el equipo de escucha (privado/público/dominio). Si el equipo de escucha no está unido a un dominio, es posible que la red aparezca como pública y, en ese caso, las reglas de firewall instaladas con el Administrador de estadísticas no se aplicarán de forma predeterminada.
    
- **4000—** Error al descargar la información del servidor desde la escucha (motivo desconocido)
    
  - **4001:** Servidor no encontrado en la topología de escucha
    
    Este error se producirá si el servidor se conecta correctamente a la escucha, pero el servidor no se agregó a la topología en la memoria caché del agente de escucha. Opciones de resolución:
    
  - Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología.](deploy.md#BKMK_ImportTopology) 
    
  - Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster alwayson de SQL), deberá agregar el agente manualmente siguiendo las instrucciones de Importación de la [topología.](deploy.md#BKMK_ImportTopology)
    
  - **4002:** Contraseña de escucha no válida
    
    La contraseña cifrada que el agente está intentando usar no coincide con la contraseña de servicio en el propio servicio de escucha. Desinstale el agente y vuelva a instalarlo con la contraseña de servicio correcta.
    
  - **4003:** Error de coincidencia de huella digital de certificado
    
    La huella digital del certificado que se proporciona al agente en el momento de la instalación no coincide con la huella digital del certificado que está usando actualmente la escucha y, por lo tanto, se rechazará la conexión. Desinstale el agente y vuelva a instalarlo con la huella digital del certificado correcta.
    
  - **4004—** Respuesta no válida o HttpStatusCode
    
    El agente de escucha no responde con un estado esperado. 
    
  - Si la conexión está en proxy, compruebe la configuración del proxy.
    
  - Compruebe si hay problemas con su configuración en el registro statsMan del equipo de escucha.
    
  - **4005:** No se pudo deserializar el XML
    
    La información del servidor en el servidor de escucha está dañada o puede haber un error de coincidencia de versiones entre el agente y los equipos de escucha. Asegúrese de que las versiones coinciden y compruebe si hay problemas en el registro de eventos de escucha.
    
## <a name="listener-events"></a>Eventos de escucha
<a name="BKMK_Listener"> </a>

- **10000:** error de inicio Motivo desconocido (estos no se pueden recuperar y el servicio se detendrá o bloqueará como resultado)
    
  - **10001:** problema de configuración
    
    Por lo general, esto ocurrirá cuando el archivo [listener_install_location]\PerfAgentListener.exe.config se haya modificado manualmente y la aplicación no pueda leerlo.
    
  - **10002:** Error de inicialización de la escucha HTTP
    
    Por lo general, este evento se registrará cuando la ACL de la dirección URL no se haya establecido correctamente durante la instalación o el certificado SSL no sea válido. Asegúrese de que el certificado de la configuración es válido. Si es así, vuelva a instalar el agente de escucha de acuerdo con las instrucciones de [Implementar el Administrador de estadísticas.](deploy.md#BKMK_Deploy)
    
  - **10003:** Error de Redis
    
  - **10004:** error de infraestructura de almacenamiento en caché
    
  - **10007:** Configuración (almacenada en redis)
    
    El agente de escucha no pudo ponerse en contacto con Redis ni recuperar datos bien formados de la memoria caché y no pudo iniciarse. Asegúrese de que el servicio Redis se ha iniciado y configurado correctamente en el servidor.
    
  - **10005:** Recuperación y análisis de información del servidor
    
    La información de topología de la memoria caché de Redis no es válida. En primer lugar, intente reiniciar Redis y la escucha. Si el error persiste, consulte [Importar la topología para](deploy.md#BKMK_ImportTopology) volver a crear los datos de la topología.
    
- **10100:** Interrupción del PING de Redis
    
  - **10101:** Interrupción continuada de PING de Redis (cada 60 segundos)
    
  - **30100:** Interrupción de PING de Redis restaurada
    
    Se registrarán cuando el agente de escucha no pueda conectarse a Redis. Asegúrese de que Redis se ha iniciado y de que la conectividad de red entre el servicio de escucha y Redis está disponible.
    
- **10200:** Interrupción de escritura de Redis
    
  - **10201:** Interrupción continuada de redis write (cada 60 segundos)
    
  - **30100:** interrupción de redis write resuelto
    
    Se registrarán cuando el agente de escucha no pueda escribir en la memoria caché de Redis. Asegúrese de que Redis se ha iniciado y de que la conectividad de red entre el servicio de escucha y Redis está disponible.
    
- **30000:** iniciado correctamente
    
    Se registra cada vez que se inicia la escucha.
    
- **22000:** la inicialización del agente del Administrador de estadísticas se ha logrado.
    
- **23000—** Inicialización de EventLogQueryManager correcta (primera vez o después de un error)
    
- **24000—** Inicialización de serverinfo correcta (primera vez o después de un error)
    
- **25000—** La escucha vuelve a estar en línea después de no publicar (o la primera publicación correcta)
    
- **5000:** Inicio del agente de escucha sin conexión para publicar datos
    
- **5001:** la escucha aún está sin conexión durante un período prolongado
    
    Estos eventos pueden ser útiles para supervisar, alertas y borrar problemas.
    
## <a name="website-issues"></a>Problemas del sitio web
<a name="BKMK_Website"> </a>

- Mensajes de inicio de sesión repetitivos en Chrome: se trata de un error que se ha resuelto en la versión 1.1. Asegúrese de que ha actualizado a la versión más reciente del Administrador de estadísticas si ve varias solicitudes de inicio de sesión en el explorador Chrome. Para comprobar la versión del sitio web que está ejecutando:
    
  - En el Explorador de archivos, abierto (directorio predeterminado)
    
  - Haga clic con el botón StatsManHubWebSite.dll y vea sus propiedades.
    
  - Si no se encuentra un equipo en la vista horizontal de KHI o en la vista Detalles del contador, asegúrese de que es miembro de un sitio y un grupo de servidores. Si no es así, no aparecerá en esas vistas. Para obtener información acerca de cómo definir un sitio y un grupo de servidores para un servidor de la topología, consulte [Importar la topología.](deploy.md#BKMK_ImportTopology)
    
  - La versión del producto se mostrará en los detalles de descripción.
    
## <a name="for-more-information"></a>Más información
<a name="BKMK_Website"> </a>

Para obtener más información, vea los artículos siguientes: 
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)
    
- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)
