---
title: Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumen: lea este tema para solucionar problemas de implementación de Statistics Manager para Skype Empresarial Server.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675282"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solucionar problemas del administrador de estadísticas para Skype Empresarial Server

**Resumen:** Lea este tema para solucionar problemas de implementación de Statistics Manager para Skype Empresarial Server.

En este tema se describe cómo solucionar problemas de la implementación de Statistics Manager describiendo los eventos que puede ver en el registro de eventos de la aplicación y las acciones adecuadas que puede realizar para corregir el evento. En este tema se presentan las siguientes secciones:

- [Eventos del agente](troubleshoot.md#BKMK_Agent)

- [Eventos de agente de escucha](troubleshoot.md#BKMK_Listener)

- [Problemas del sitio web](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>Eventos del agente
<a name="BKMK_Agent"> </a>

- **1000** — No se puede configurar el limitador de procesador (objeto de trabajo) — Motivo desconocido

- **1001** : no se permite la limitación de procesos en el proceso (probablemente ya está dentro de un objeto de trabajo)

    El agente se ejecuta dentro de un objeto de trabajo de Windows para limitar automáticamente su superficie de memoria. Si el agente no se iniciará y estas entradas de evento están presentes en el registro de eventos, no se puede crear una instancia del objeto de trabajo en el servidor. Para solucionar este problema, se puede quitar el límite superior de memoria cambiando un valor en el archivo de configuración:

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Busque "MaxProcessMemoryMB" y cambie el valor a "0", como se muestra:

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si se realiza este cambio, el agente generalmente seguirá usando \< 100 MB de memoria, pero no se limitará por fuerza a 300 MB como es el valor predeterminado. Si se realiza este cambio, se recomienda supervisar estrechamente el uso de memoria para asegurarse de que el agente no consume una gran cantidad de memoria en su máquina host.

- **2000** : error de inicialización del cliente

- **2001**: no se pudo establecer ninguna conexión con el servicio en ninguna dirección IP de origen

  Si el agente no puede conectarse al equipo del agente de escucha, compruebe lo siguiente:

  1. Asegúrese de que el servicio de escucha se está ejecutando en el equipo de escucha. Si no es así, asegúrese de que Redis se ejecuta en ese servidor y, a continuación, reinicie el servicio de escucha.

     Compruebe el registro de eventos del Administrador de estadísticas en el equipo de escucha para asegurarse de que no hay ningún problema con el propio servicio de escucha del Administrador de estadísticas.

  2. Use una herramienta de conectividad como telnet para comprobar la conectividad desde el equipo del agente al agente de escucha en el puerto correcto.

     Si no es así, asegúrese de que la regla de firewall entrante está habilitada en el equipo de escucha para el tipo de red al que está conectado el equipo de escucha (privado/público/dominio). Si el equipo de escucha no está unido a un dominio, la red puede aparecer como pública y, en ese caso, las reglas de firewall instaladas con el Administrador de estadísticas no se aplicarán de forma predeterminada.

- **4000** : error al descargar la información del servidor del agente de escucha (motivo desconocido)

  - **4001** : servidor no encontrado en la topología del agente de escucha

    Este error se producirá si el servidor se conecta correctamente al agente de escucha, pero el servidor no se agregó a la topología en la memoria caché del agente de escucha. Opciones de resolución:

  - Asegúrese de seguir las instrucciones para importar la topología. Consulte [Importación de la topología](deploy.md#BKMK_ImportTopology).

  - Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster de AlwaysOn SQL), deberá agregar el agente manualmente siguiendo las instrucciones de [Importación de la topología](deploy.md#BKMK_ImportTopology).

  - **4002** : contraseña de agente de escucha no válida

    La contraseña cifrada que el agente intenta usar no coincide con la contraseña del servicio en el propio agente de escucha. Desinstale el agente y vuelva a instalarlo con la contraseña de servicio correcta.

  - **4003** : error de coincidencia de huella digital del certificado

    La huella digital del certificado que se proporciona al agente en el momento de la instalación no coincide con la huella digital del certificado que el agente de escucha está usando actualmente y, por tanto, se rechazará la conexión. Desinstale el agente y vuelva a instalarlo con la huella digital del certificado correcta.

  - **4004** : respuesta no válida o HttpStatusCode

    El agente de escucha no responde con un estado esperado.

  - Si la conexión es proxy, compruebe la configuración del proxy.

  - Compruebe el registro StatsMan del equipo de escucha para ver si hay problemas con su configuración.

  - **4005** : no se pudo des serializar el XML

    La información del servidor en el servidor de escucha está dañada o puede haber una falta de coincidencia de versión entre el agente y los equipos del agente de escucha. Asegúrese de que las versiones coinciden y compruebe si hay problemas en el registro de eventos del agente de escucha.

## <a name="listener-events"></a>Eventos de agente de escucha
<a name="BKMK_Listener"> </a>

- **10000** : error de inicio Motivo desconocido (estos son irrecuperables y el servicio se detendrá o se bloqueará como resultado)

  - **10001** : problema de configuración

    Por lo general, esto ocurrirá cuando el archivo [listener_install_location]\PerfAgentListener.exe.config se haya modificado manualmente y la aplicación no pueda leerlo.

  - **10002** : error de inicialización del agente de escucha HTTP

    Por lo general, este evento se registrará cuando la ACL de dirección URL no se haya establecido correctamente durante la instalación o el certificado SSL no sea válido. Asegúrese de que el certificado de la configuración es válido. Si es así, vuelva a instalar el agente de escucha de acuerdo con las instrucciones de [Implementación del Administrador de estadísticas](deploy.md#BKMK_Deploy).

  - **10003** : error de Redis

  - **10004** : error de infraestructura de almacenamiento en caché

  - **10007** — Configuración (almacenados en redis)

    El agente de escucha no pudo ponerse en contacto con Redis ni recuperar datos bien formados de la memoria caché y no pudo iniciarse. Asegúrese de que el servicio Redis se ha iniciado y configurado correctamente en el servidor.

  - **10005** : recuperación y análisis de información del servidor

    La información de topología de la caché de Redis no es válida. En primer lugar, intente reiniciar Redis y el agente de escucha. Si el error persiste, consulte [Importación de la topología](deploy.md#BKMK_ImportTopology) para volver a crear los datos de la topología.

- **10100** : interrupción del PING de Redis

  - **10101** : Interrupción continua del PING de Redis (cada 60 segundos)

  - **30100** : se restauró la interrupción de PING de Redis

    Se registrarán cuando el agente de escucha no pueda conectarse a Redis. Asegúrese de que Redis se inicia y que la conectividad de red entre el agente de escucha y Redis está disponible.

- **10200** : interrupción de escritura de Redis

  - **10201** : Interrupción de la escritura de Redis continuada (cada 60 segundos)

  - **30100** : interrupción de escritura de Redis resuelta

    Se registrarán cuando el agente de escucha no pueda escribir en la caché de Redis. Asegúrese de que Redis se inicia y que la conectividad de red entre el agente de escucha y Redis está disponible.

- **30000** : iniciado correctamente

    Se registra cada vez que se inicia el agente de escucha.

- **22000** : la inicialización del agente de Statistics Manager se realizó correctamente.

- **23000** : la inicialización de EventLogQueryManager se realizó correctamente (primera vez o después de un error)

- **24000** : la inicialización de serverinfo se realizó correctamente (primera vez o después de un error)

- **25000** : el agente de escucha vuelve a estar en línea después de no publicar (o la primera publicación correcta)

- **5000** : inicio del agente de escucha sin conexión para publicar datos

- **5001** : el agente de escucha sigue sin conexión durante un período prolongado

    Estos eventos pueden ser útiles para supervisar, alertar o borrar problemas.

## <a name="website-issues"></a>Problemas del sitio web
<a name="BKMK_Website"> </a>

- Mensajes de inicio de sesión repetitivos en Chrome: se trata de un error que se ha resuelto en la versión 1.1. Asegúrese de que ha actualizado a la versión más reciente del Administrador de estadísticas si ve mensajes de inicio de sesión repetidos en el explorador Chrome. Para comprobar la versión del sitio web que está ejecutando:

  - En Explorador de archivos, abra (directorio predeterminado)

  - Haga clic con el botón derecho en StatsManHubWebSite.dll y vea sus propiedades.

  - Si no se puede encontrar un equipo en la vista horizontal de KHI o en la vista Detalles del contador, asegúrese de que es miembro de un sitio y un grupo. Si no es así, no aparecerá en esas vistas. Para obtener información sobre cómo definir un sitio y un grupo para un servidor en la topología, consulte [Importación de la topología](deploy.md#BKMK_ImportTopology).

  - La versión del producto se mostrará en los detalles de la descripción.

## <a name="for-more-information"></a>Más información
<a name="BKMK_Website"> </a>

Para obtener más información, vea los artículos siguientes: 

- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)

- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)

- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)
