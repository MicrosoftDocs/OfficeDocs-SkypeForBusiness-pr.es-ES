---
title: Solucionar problemas de instalación y actualización de Microsoft Teams en Windows
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo solucionar problemas de instalación y actualización de la aplicación cliente de escritorio de Teams en Windows.
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920160"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Solucionar problemas de instalación y actualización de Microsoft Teams en Windows

Este artículo proporciona instrucciones para diagnosticar y solucionar problemas de instalación y actualización de la aplicación cliente de escritorio de teams que se ejecuta en Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Comprobar si Teams se ha actualizado correctamente

Siga estos pasos para comprobar si se ha instalado correctamente una actualización de Teams.

1. En Teams, seleccione su imagen de perfil y, a continuación, haga clic en **acerca de** > la**versión**.
2. En el mismo menú, haga clic en **Buscar actualizaciones**.
3. Espere a que el banner de la parte superior de la aplicación indique que se necesita una "actualización" de Teams. El vínculo debe mostrarse un minuto después, ya que este proceso descarga la nueva versión de Teams. La pancarta también le permite saber si ya está ejecutando la última versión, en cuyo caso no es necesario realizar ninguna actualización.
4. Haga clic en el vínculo actualizar de la pancarta.
5. Espere hasta que se reinicie Teams y, después, repita el paso 1 para ver si la aplicación se ha actualizado.

Si ve un mensaje de error o si el número de versión es el mismo que en el paso 4, se produjo un error en el proceso de actualización.

## <a name="troubleshoot-installation-and-update-issues"></a>Solucionar problemas de instalación y actualización

### <a name="troubleshoot-installation-issues"></a>Solucionar problemas de instalación

Cuando se instala Teams, el instalador de Teams registra la secuencia de eventos en%LocalAppData%\SquirrelTemp\SquirrelSetup.log. Lo primero que hay que buscar es un mensaje de error o una pila de llamadas cerca del final del registro. Tenga en cuenta que las pilas de llamadas al principio del registro pueden no significar que exista un problema de instalación. Puede ser más fácil comparar el registro con el registro de una instalación correcta (incluso en otro equipo) para ver lo que se espera.

Si SquirrelSetup. log no indica la causa o si necesita más información para solucionar el problema, consulte [recopilar y analizar los registros del sistema y](#collect-and-analyze-application-and-system-logs)de la aplicación.

### <a name="troubleshoot-update-issues"></a>Solucionar problemas de actualización

Cuando Teams se instala correctamente, la ubicación del registro cambia de%LocalAppData%\SquirrelTemp a%AppData%\Microsoft\Teams. En esta ubicación, hay dos archivos de registro de interés, SquirrelSetup. log y logs. txt.

- El archivo SquirrelSetup. log de esta ubicación está escrito por Update. exe, que es un archivo ejecutable que se aplica a la aplicación de Teams.
- El archivo logs. txt es utilizado por la aplicación de Teams (en concreto, Teams. exe) para grabar eventos de aplicación importantes. Es probable que contenga información de error.

Estos archivos de registro contienen información de identificación personal (PII) y, por lo tanto, no se envían a Microsoft.

Teams puede iniciar automáticamente el proceso de actualización (según la Directiva) o los usuarios pueden buscar actualizaciones de forma manual yendo a su imagen de perfil > **comprobar si hay actualizaciones**. Ambos métodos usan la siguiente secuencia de eventos.

1. **Comprobar si hay actualizaciones**. Teams realiza una solicitud Web e incluye la versión de la aplicación actual y la información del timbre de implementación. El objetivo de este paso es obtener el vínculo de descarga. En este paso, se registra un error en logs. txt.
2. **Descargar actualización**. Teams descarga la actualización mediante el vínculo de descarga obtenido en el paso 1. Una vez completada la descarga, Teams llama a Update. exe para ensayar la descarga. También se ha registrado un error de descarga en logs. txt.
3. **Ensayar la actualización**. El contenido descargado se verifica y se desempaqueta en una carpeta intermedia,%LocalAppData%\Microsoft\Teams\stage), que se realiza mediante Update. exe. Los errores en este paso se registran en SquirrelTemp. log.
4. **Instale la actualización**. Hay varias maneras de iniciar Teams. El sistema inicia automáticamente Teams cuando un usuario inicia sesión o puede iniciar Teams a través de un acceso directo. En este paso, Update. exe comprueba la presencia de la carpeta de ensayo, verifica el contenido de nuevo y realiza operaciones de archivo para que no se desactive la aplicación. Se realiza una copia de seguridad de la antigua carpeta de la aplicación en%LocalAppData%\Microsoft\Teams\current y se cambia el nombre de la carpeta Stage a "Current". Los errores en este paso se registran en SquirrelTemp. log.

Si SquirrelTemp. log o. txt no contienen información suficiente para determinar la causa subyacente y necesita más información para solucionar el problema, vaya a [recopilar y analizar los registros del sistema y](#collect-and-analyze-application-and-system-logs)de la aplicación.

## <a name="collect-and-analyze-application-and-system-logs"></a>Recopilar y analizar los registros del sistema y de la aplicación

En esta sección se describe cómo recopilar y analizar los registros del sistema y de la aplicación para obtener información más completa para solucionar el problema. Puede usar las herramientas de Sysinternals para completar estos pasos. Para obtener más información, vea [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Recopilar registros

1. Descargue las [herramientas de Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraiga el archivo zip a la carpeta% TEMP% en la unidad local.
3. Abra un símbolo del sistema con privilegios elevados y, a continuación, haga lo siguiente:

    1. Ejecute lo siguiente para ir a la carpeta TEMP:

        ```
        cd /d %TEMP%
        ```
    2. Copie los registros de configuración y aplicación. Tenga en cuenta que, según el punto de error, es posible que algunos de estos registros no estén presentes.

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Ejecute lo siguiente para capturar los identificadores abiertos.

        ```
        handle > handles.txt
        ```

    4. Ejecute lo siguiente para capturar los archivos dll abiertos.

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. Ejecute lo siguiente para capturar los drivers que se están ejecutando.

        ```
        driverquery /v > driverquery.txt
        ```

    6. Ejecute lo siguiente para capturar las listas de control de acceso (ACL) de la carpeta Teams.

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analizar registros (para usuarios avanzados)

Una actualización fallida puede dar lugar A un comportamiento impredecible de la aplicación. Por ejemplo, es posible que los usuarios no puedan salir de Teams, tener una versión obsoleta de Teams o no puedan iniciar Teams. Si experimenta un problema durante una actualización, el primer lugar en el que debe buscar la causa es SquirrelTemp. log. Estos son los distintos tipos de errores de actualización, enumerados de lo más común a lo menos común, y cómo analizarlos y solucionarlos mediante registros.

#### <a name="unable-to-exit-teams"></a>No se puede salir de Teams

Puesto que Teams determina que necesita actualizarse a una versión más reciente, descarga y fases la nueva aplicación y, a continuación, espera a que se reinicie por sí mismo la próxima vez que el equipo esté inactivo. Un problema común durante este proceso es cuando otro proceso o un controlador de sistema de archivos bloquea el proceso Teams. exe, lo que evita que se cierre Team. exe. Como resultado, la aplicación de Teams no se puede reemplazar con la aplicación que se acaba de descargar y se ha preconfigurado.

Sugerencias para la solución de problemas:

- Para confirmar que se trata del problema, salga de Teams (haga clic con el botón secundario en Teams en la barra de tareas y, a continuación, haga clic en **salir**). A continuación, abra el administrador de tareas de Windows para ver si una instancia de Teams aún se está ejecutando.  
- Si no está en el equipo que tiene este problema, inspeccione el SquirrelTemp. log recopilado en el equipo que está experimentando este problema y busque la entrada "programa: no se puede finalizar el proceso en el registro".
- Para determinar qué impide la salida de Teams. exe, mire los archivos dll. txt y administre los registros. txt. Le indican los procesos que evitaron que los equipos se cierren.
- Otra causa que puede impedir que los equipos salgan es el controlador de filtro de sistema de archivos en el modo de núcleo. Use la herramienta SysInternals, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), para recopilar el volcado del proceso de modo de ```procdump -mk <pid>```núcleo ejecutando <pid> , donde es el identificador de proceso obtenido desde el administrador de tareas. También puede inspeccionar el archivo de registro DRIVERQUERY. txt para ver los controladores de filtro activos que pueden interferir con Teams.
- Para recuperar a partir de este estado, reinicie el equipo.

#### <a name="file-permissions"></a>Permisos de archivo

Teams crea una serie de subcarpetas y archivos en el perfil del usuario durante el proceso de instalación y actualización. Como la aplicación y el actualizador se ejecutan como un usuario no elevado, se deben conceder permisos de lectura y escritura en las carpetas siguientes:

|Carpetas  |Utilizado por  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Instalador de Teams (por ejemplo, Teams_Windows_x64. exe) durante la fase de instalación        |
|%LocalAppData%\Microsoft\Teams  | Actualizador de equipos (Update. exe) para extraer y ensayar el paquete de la aplicación durante el proceso de actualización        |
|%AppData%\Microsoft\Teams   |  Aplicación de Teams (Teams. exe) para guardar la configuración, los Estados de la aplicación y el paquete de actualización descargado (preconfigurado)       |

Si se le deniega el acceso a teams porque no puede escribir en un archivo, es posible que otra aplicación de software esté interfiriendo o que una entrada de descriptor de seguridad limite el acceso de escritura a una carpeta.

Sugerencias para la solución de problemas:

- Busque evidencia "acceso denegado" en SquirrelTemp. log o logs. txt. Compruebe estos archivos para ver si hubo un intento de escribir en un archivo que ha fallado.
- Abra icacls. txt y busque la entrada de control de acceso (ACE) efectiva que bloquea las operaciones de escritura por un usuario que no es un administrador. Normalmente, se encuentra en una de las entradas DACL. Para obtener más información, consulte la [documentación de icacls](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Archivo dañado

En algunos casos, el software de cifrado puede cambiar los archivos de la carpeta%LocalAppData%\Microsoft\Teams, lo que puede impedir que se inicie Teams. Esto puede suceder en cualquier momento, incluso cuando la aplicación no se actualiza. Lamentablemente, cuando un archivo está dañado, la única forma de recuperar a partir de este estado es desinstalar y volver a instalar Teams.

> [!NOTE]
> Si no puede determinar la causa subyacente del problema usando alguno de estos pasos, es posible que desee probar una sesión de [monitor de proceso](https://docs.microsoft.com/sysinternals/downloads/procmon) . Process Monitor es una herramienta de Sysinternals que registra el acceso al registro y al sistema de archivos.

## <a name="related-topics"></a>Temas relacionados

- [Obtener clientes para Microsoft Teams](get-clients.md)
- [Actualizaciones del cliente de Teams](teams-client-update.md)