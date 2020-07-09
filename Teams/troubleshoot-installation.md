---
title: Solución de problemas de instalación y actualización de Microsoft Teams en Windows
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo solucionar problemas de instalación y actualización de la aplicación cliente de escritorio de Teams en Windows.
ms.openlocfilehash: 7b8d4984a8ee40f9a013155ad28b682e000260ba
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086146"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Solución de problemas de instalación y actualización de Microsoft Teams en Windows

Este artículo le proporciona instrucciones sobre cómo diagnosticar y solucionar problemas de instalación y actualización de la aplicación cliente de escritorio de Teams que se ejecuta en Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Comprobar si Teams se ha actualizado correctamente

Siga estos pasos para comprobar si una actualización de Teams se ha instalado correctamente.

1. En Teams, seleccione su imagen de perfil y, después, haga clic en **Acerca de** > **Versión**.
2. En el mismo menú, haga clic en **Buscar actualizaciones**.
3. Espere a que el mensaje emergente de la parte superior de la aplicación indique que es necesario "actualizar" Teams. El vínculo debería mostrarse un minuto más tarde, ya que este proceso descarga la nueva versión de Teams. El mensaje emergente también le permite saber si ya está ejecutando la última versión en cuyo caso, no es necesario realizar ninguna actualización.
4. Haga clic en el vínculo de actualización en el mensaje emergente.
5. Espere a que se reinicie Teams y, después, repita el paso 1 para ver si la aplicación se actualiza.

Si ve un mensaje de error o si el número de versión es igual que en el paso 4, el proceso de actualización no se realizó correctamente.

## <a name="troubleshoot-installation-and-update-issues"></a>Solución de problemas de instalación y actualización

### <a name="troubleshoot-installation-issues"></a>Solución de problemas de instalación

Cuando se instala Teams, el programa de instalación de Teams registra la secuencia de eventos en %LocalAppData%\SquirrelTemp\SquirrelSetup.log. Lo primero que hay que buscar es un mensaje de error o una pila de llamadas cerca del final del registro. Tenga en cuenta que las pilas de llamadas al comienzo del registro pueden no significar que existe un problema de instalación. Puede ser más fácil comparar el registro con el registro de una instalación correcta (incluso en otro equipo) para ver lo que se espera.

Si SquirrelSetup.log no indica la causa o si necesita más información para solucionar el problema, vea [Recopilar y analizar los registros del sistema y de la aplicación](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Solución de problemas de actualización

Cuando Teams se instala correctamente, la ubicación del registro cambia de %LocalAppData%\SquirrelTemp a %AppData%\Microsoft\Teams. En esta ubicación, hay dos archivos de registro interesantes, SquirrelSetup.log y logs.txt.

- El archivo SquirrelSetup.log en esta ubicación está escrito por Update.exe, que es un archivo ejecutable que se aplica a la aplicación Teams.
- El archivo Logs.txt se usa en la aplicación Teams (especialmente en Teams.exe) para registrar eventos de aplicación importantes. Es probable que contenga información de error.

Estos archivos de registro contienen información de identificación personal (PII), por lo que no se envían a Microsoft.

Teams puede iniciar automáticamente el proceso de actualización (según la directiva) o los usuarios pueden buscar las actualizaciones manualmente yendo a su imagen de perfil > **Buscar actualizaciones**. Ambos métodos usan la siguiente secuencia de eventos.

1. **Busque actualizaciones**. Teams realiza una solicitud web e incluye la versión actual de la aplicación y la información sobre el anillo de implementación. El objetivo de este paso es obtener el vínculo de descarga. Un error en este paso se registra en Logs.txt.
2. **Descargue la actualización**. Teams descarga la actualización mediante el vínculo de descarga obtenido en el paso 1. Una vez completada la descarga, Teams llama a Update.exe para preparar la descarga. Los errores de descarga también se registran en Logs.txt.
3. **Prepare la actualización**. El contenido descargado se verifica y se desempaqueta en una carpeta intermedia, %LocalAppData%\Microsoft\Teams\stage, que se lleva a cabo mediante Update.exe. Los errores de este paso se registran en SquirrelTemp.log.
4. **Instale la actualización**. Hay varias formas de iniciar Teams. El sistema inicia automáticamente Teams cuando un usuario inicia sesión o cuando inicie Teams mediante un acceso directo. En este paso, Update.exe comprueba la presencia de la carpeta provisional, vuelve a comprobar el contenido y realiza operaciones de archivo para quitar la aplicación de la fase de preparación. Se realiza una copia de seguridad de la antigua carpeta de la aplicación que estaba en %LocalAppData%\Microsoft\Teams\current en %LocalAppData%\Microsoft\Teams\previous y se cambia el nombre de la carpeta provisional a "actual". Los errores de este paso se registran en SquirrelTemp.log.

Si SquirrelTemp.log o Logs.txt no contienen información suficiente para determinar la causa subyacente y necesita más información para solucionar el problema, vaya a [Recopilar y analizar los registros del sistema y de la aplicación](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Recopilar y analizar los registros del sistema y de la aplicación

En esta sección, se describe cómo recopilar y analizar los registros del sistema y de la aplicación para obtener información más completa para solucionar el problema. Use las herramientas de Sysinternals para completar estos pasos. Para obtener más información, vea [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Recopilar registros

1. Descargue las [herramientas de Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraiga el archivo zip en la carpeta %TEMP% de la unidad local.
3. Abra un símbolo del sistema con privilegios elevados y, después, haga lo siguiente:

    1. Ejecute lo siguiente para ir a la carpeta TEMP:

        ```console
        cd /d %TEMP%
        ```
    2. Copie los registros de la aplicación y de configuración. Tenga en cuenta que, en función del momento del error, es posible que algunos de estos registros no estén presentes.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Ejecute lo siguiente para capturar los controladores abiertos.

        ```console
        handle > handles.txt
        ```

    4. Ejecute lo siguiente para capturar los archivos dll abiertos.

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. Ejecute lo siguiente para capturar los controladores que se están ejecutando.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Ejecute lo siguiente para capturar las listas de control de acceso (ACL) de la carpeta Teams.

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analizar registros (para usuarios avanzados)

Una actualización no correcta puede provocar un comportamiento de la aplicación imprevisible. Por ejemplo, es posible que los usuarios no puedan cerrar Teams, que tengan una versión obsoleta o que no puedan iniciar el programa. Si experimenta un problema durante una actualización, el primer sitio en el que buscar la causa es SquirrelTemp.log. Aquí se muestran los diferentes tipos de errores de actualización, enumerados del más común al menos común, y cómo analizarlos y solucionarlos mediante registros.

#### <a name="unable-to-exit-teams"></a>No se pueden cerrar Teams

Cuando Teams determina que necesita actualizarse a una versión más reciente, descarga y prepara la aplicación nueva y, después, espera la oportunidad de reiniciarse la próxima vez que el equipo esté inactivo. Un problema habitual durante este proceso ocurre cuando otro proceso o un controlador del sistema de archivos bloquea el proceso de Teams.exe, lo que impide el cierre de Teams.exe. Por lo tanto, la aplicación Teams no puede reemplazarse por la aplicación recién descargada y preparada.

Sugerencias para la solución de problemas:

- Para confirmar que es el problema que está experimentando, cierre Teams (haga clic con el botón derecho en Teams en la barra de tareas y, después, haga clic en **Cerrar**). A continuación, abra el Administrador de tareas en Windows para ver si aún se está ejecutando una instancia de Teams.  
- Si no se encuentra en el equipo que está experimentando este problema, inspeccione el SquirrelTemp.log recopilado en el equipo donde se produce y busque una entrada "Programa: no se puede finalizar el proceso en el registro".
- Para determinar qué impide cerrar Teams.exe, mire los registros Dlls.txt y Handles.txt. Estos son los procesos que impidieron el cierre de Teams.
- Otra culpable que puede impedir el cierre de Teams es el controlador de filtro del sistema de archivos en el modo kernel. Use la herramienta SysInternals, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), para recopilar el volcado del proceso en modo kernel al ejecutar ```procdump -mk <pid>```, donde <pid> es el ID. del proceso obtenido del Administrador de tareas. También puede inspeccionar el archivo de registro Driverquery.txt para ver los controladores de filtro activos que pueden interferir con Teams.
- Para recuperarse de este estado, reinicie el equipo.

#### <a name="file-permissions"></a>Permisos de archivos

Teams crea una serie de subcarpetas y archivos en el perfil de usuario durante el proceso de instalación y actualización. Dado que la aplicación y el actualizador se ejecutan como un usuario sin privilegios elevados, deben concederse permisos de lectura y escritura en las carpetas siguientes:

|Carpeta  |Usada por  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Instalador de Teams (por ejemplo, Teams_Windows_x64.exe) durante la fase de instalación        |
|%LocalAppData%\Microsoft\Teams  | Actualizador de Teams (Update.exe) para extraer y preparar el paquete de la aplicación durante el proceso de actualización        |
|%AppData%\Microsoft\Teams   |  Aplicación de Teams (Teams.exe) para guardar la configuración, los estados de la aplicación y el paquete de actualización descargado (preconfigurado)       |

Si se deniega el acceso a Teams porque no puede escribir en un archivo, puede que otra aplicación de software interfiera o que una entrada del descriptor de seguridad limite el acceso de escritura a una carpeta.

Sugerencias para la solución de problemas:

- Busque la evidencia "acceso denegado" en SquirrelTemp.log o Logs.txt. Compruebe estos archivos para ver si se ha intentado escribir en un archivo con errores.
- Abra Icacls.txt y busque la entrada de control de acceso (ACE) efectiva que bloquea las operaciones de escritura de un usuario que no es administrador. Normalmente, se encuentra en una de las entradas DACL. Para obtener más información, vea la [Documentación de icacls](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Archivo dañado

En algunos casos, el software de cifrado puede cambiar archivos en la carpeta %LocalAppData%\Microsoft\Teams, lo que puede impedir iniciar Teams. Esto puede ocurrir en cualquier momento, incluso cuando la aplicación no se actualiza. Por desgracia, cuando un archivo está dañado, la única forma de recuperarse desde este estado es desinstalar y volver a instalar Teams.

> [!NOTE]
> Si no puede determinar la causa subyacente del problema utilizando cualquiera de estos pasos, es posible que quiera probar una sesión del [Monitor de procesos](https://docs.microsoft.com/sysinternals/downloads/procmon). Monitor de procesos es una herramienta de Sysinternals que registra el acceso al registro y al sistema de archivos.

## <a name="related-topics"></a>Temas relacionados

- [Obtener clientes para Microsoft Teams](get-clients.md)
- [Actualizaciones del cliente de Teams](teams-client-update.md)
- [Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)