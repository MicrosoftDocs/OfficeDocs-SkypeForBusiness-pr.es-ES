---
title: Notas de la versión de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf95a95c02ad37abdbf88f235cff2f0d5b0459a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Notas de la versión para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

Bienvenido a las notas de la versión de Lync Server 2013. Consulte este archivo para obtener información sobre problemas conocidos de Lync Server 2013.

<div>

## <a name="about-this-document"></a>Acerca de este documento

Este documento contiene información importante que debe conocer antes de implementar y usar Lync Server 2013. Para obtener más información sobre Lync Server 2013, consulte la documentación de [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

En este documento se presentan las siguientes secciones:

  - Cliente de Lync 2013

  - Lync Server

  - Instalación

  - Movilidad

  - Conferencia

  - Telefonía IP empresarial

  - Presencia

  - Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

  - Panel de control de Lync Server, Generador de topologías y Herramienta de planeación

  - Localización

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Cliente de Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>La transferencia de un archivo en un mensaje instantáneo produce un error si el archivo está abierto en otra aplicación

**Emitir**

Si intenta transferir un archivo, como un documento de Word, si lo incluye en un mensaje instantáneo a otro usuario de Lync, la transferencia parecerá que es correcta, pero es posible que, en realidad, no pueda transferir el archivo. Se mostrará un icono para el tipo de archivo en el cliente de Lync, pero el destinatario previsto no podrá abrir el archivo. No se muestra ningún mensaje de error para informarle de que la transferencia no se ha realizado correctamente.

**Evitar**

Para solucionar este problema, cierre el archivo o aplicación abierto que lo tiene abierto antes de intentar transferir el archivo en un mensaje instantáneo.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Si se produce un error en la replicación de datos del servicio de almacenamiento de Lync Server, los administradores deberán comprobar los contadores de rendimiento de los elementos de la cola del servicio de almacenamiento obsoleto

**Emitir**

El servicio de almacenamiento de Lync Server usa Windows fabric para la replicación. Si los datos se eliminan en un servidor front-end principal, pero se produce un error en la eliminación de un servidor front-end secundario (por ejemplo, si hay un apagado inesperado o un error en el servidor front-end), los datos pueden quedar "huérfanos". Los datos huérfanos pueden provocar la degradación del rendimiento y la pérdida de espacio en la unidad.

**Evitar**

Para solucionar este problema, si se generan los eventos\_LYSS\_espacio\_\_de base de datos (ID = 32058)\_y\_LYSS\_espacio\_de base de datos usado crítico (ID = 32059) en el registro de eventos, los administradores deben comprobar el contador de rendimiento en el servidor front-end en **LS: LYSS-API del servicio** de almacenamiento con el nombre **LYSS-Current número de elementos de cola obsoletos**. Si este contador de rendimiento tiene un valor alto (por ejemplo, mayor que 50000), el administrador debe ejecutar la herramienta CleanuUpStorageServiceData. exe en el kit de recursos de Lync Server 2013, que eliminará todos los datos huérfanos del grupo. Para obtener más información sobre la herramienta, consulte la documentación del kit de recursos de Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Siempre que se cambia la configuración de la dirección IP de un servidor o grupo de servidores, es necesario reiniciar los servicios de Lync Server.

**Emitir**

Cuando se cambia la configuración de la dirección IP para una implementación de Lync Server 2013, como cambiar de IPv4 a pila dual o de pila dual a IPv6, no todos los componentes del servidor toman el cambio de configuración hasta que se reinicien los servicios.

**Evitar**

Para solucionar este problema, reinicie los servicios de Lync Server después de cambiar la configuración de la dirección IP de la implementación. Para ello, ejecute los siguientes cmdlets en el shell de administración de Lync Server:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>El cmdlet de transacciones sintéticas de conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013

**Emitir**

El cmdlet **Test-CsDialInConferencing** de la transacción sintética de conferencia de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013.

**Evitar**

El cmdlet de transacciones sintéticas de conferencia de acceso telefónico local **Test-CsDialInConferencing** solo se puede usar en una empresa de forma interna.

Los administradores pueden seguir usando el cmdlet en el shell de administración de Lync Server para fines de solución de problemas. Si es necesario, una empresa también puede desarrollar un módulo de administración privado para ejecutar el cmdlet de forma interna.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>El servicio de registro centralizado se detiene si el tráfico de red se interrumpe cuando los archivos de registro se copian a un recurso compartido de red

**Emitir**

Cuando el servicio de registro centralizado se configura para usar una ruta de red (el valor del parámetro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** es una ruta UNC válida), los archivos de registro almacenados en caché se copian al recurso compartido de red. Si se produce una interrupción en el tráfico de red mientras se copian los archivos, se generará una excepción que provocará que el servicio de registro centralizado se detenga.

El servicio está configurado para reiniciarse automáticamente hasta tres veces y, por lo tanto, se recuperará de las primeras tres excepciones.

**Evitar**

No existe ninguna solución para este problema. Para identificar el problema, supervise el identificador de evento 7031 en el registro de eventos de la "Administrador de control de servicios" que registra cuando el servicio "agente de servicio de registro centralizado de Lync Server" ha finalizado de forma inesperada. Si esto sucede más de tres veces, reinicie el servicio manualmente con el cmdlet **Start-CsWindowService**.

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Los elementos de la cola del servicio de almacenamiento deben importarse manualmente

**Emitir**

Lync Server 2013 almacena datos sobre conferencias y mensajería instantánea, como mensajes archivados y registro detallado de llamadas (CDR), en una base de datos en cada servidor front-end. Los datos se almacenan en la base de datos mientras se procesan antes de que se entreguen al destino previsto. Para mejorar el rendimiento, Lync Server 2013 exporta periódicamente los elementos de la cola de la base de datos local que no se procesan durante un período de tiempo prolongado, y los guarda en el almacén de archivos. Si el almacén de archivos no está disponible, los elementos se almacenan en cada servidor front-end. La misma operación se realiza para evitar la pérdida de datos durante la conmutación por error del grupo de servidores.

Durante la operación de exportación, el servicio de almacenamiento de Lync Server registra todas las fases en el registro de eventos con los identificadores de evento de 32075 (se inicia la operación de vaciado completa), 32076 (vaciado completo), 32082 (se inicia el vaciado de nivel de mantenimiento), 32083 (vaciado de nivel de mantenimiento se ha completado), 32089 (vaciado debido a rellenar la base de datos). Estos datos no se importarán automáticamente al sistema para ser procesados y entregados a su destino final (SQL Server o Exchange Server).

**Evitar**

Para importar los datos al sistema, los administradores deberán usar la herramienta ImportStorageServiceData del kit de recursos de Lync Server, que agregará los datos de vuelta al sistema para que se procesen y entreguen a su destino final.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Se producirá un error en las búsquedas de consulta Web de la libreta de direcciones si el valor predeterminado de UseNormalizationRules se cambia a false.

**Emitir**

Si el valor predeterminado de UseNormalizationRules se cambia a False, se producirá un error en las búsquedas de la consulta web de la libreta de direcciones. Tras modificar el valor predeterminado, los usuarios del cliente de Lync no podrán usar la consulta web de la libreta de direcciones de Lync para buscar usuarios.

**Evitar**

Si el valor predeterminado de UseNormalizationRules se establece en false para que los usuarios puedan usar los números de teléfono definidos en los servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, haga lo siguiente para solucionar este problema:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Realice una de las acciones siguientes:
    
      - Si la implementación incluye solo servidores de Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de UseNormalizationRules y IgnoreGenericRules a true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere hasta que la replicación de CMS se complete en todos los grupos de servidores.

4.  Modifique el archivo de reglas de normalización del teléfono de su implementación para borrar el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de 2013 de Lync Server. Si el archivo no está presente, cree un archivo vacío denominado "reglas de\_\_normalización\_\_de números de teléfono de la compañía. txt".

5.  Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de la implementación.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>El evento de error del servidor de libreta de direcciones 21054 se genera una vez al día para cada grupo de Lync 2013

**Emitir**

El servidor de la libreta de direcciones 2013 de Lync Server generará el evento de error 21054 una vez al día al realizar el mantenimiento diario. El error también se genera cada vez que un administrador ejecuta el cmdlet **Update-csAddressBook** , incluso cuando la actualización se ha realizado correctamente. Sin embargo, este evento de error puede omitirse con seguridad cuando la actualización se haya realizado correctamente.

**Evitar**

Cuando detecta este evento de error, ejecute el siguiente cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si el cmdlet informa de que no hay objetos no indizados o abandonados, el evento de error 21054 se puede omitir sin problemas.

Además, se debe desactivar el indicador clave de estado (KHI) de los usuarios de libreta de direcciones indizados correctamente en System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Las solicitudes pueden producir un error cuando se configura IPv6 en un grupo de servidores perimetrales

**Emitir**

Cuando se configura IPv6 en un grupo de servidores perimetrales, es posible que algunas solicitudes enviadas al grupo presenten errores.

**Evitar**

Para solucionar este problema, no configure IPv6 en un grupo de servidores perimetrales.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>El cmdlet Invoke-csPoolFailback puede fallar durante la conmutación por recuperación del grupo

**Emitir**

Al intentar la conmutación por recuperación de un grupo de servidores, el cmdlet **invoke-csPoolFailback** puede generar un error que indica que no se pudo al completar el proceso de hidratación tras varios intentos.

**Evitar**

Para solucionar este problema, ejecute el cmdlet de nuevo y espere hasta que se complete correctamente. Tenga en cuenta que el proceso de conmutación por recuperación puede tardar varios minutos en completarse. Puede tardar hasta 60 minutos para un grupo de servidores con 20.000 usuarios.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Se pueden producir pérdidas de datos cuando se agrega un servidor front-end a un grupo ya establecido: híbrido, Skype empresarial online

**Emitir**

Este problema se puede producir en un entorno en el que un grupo tiene más de un servidor front-end y se reinicia uno de los servidores front-end, o bien se agrega un nuevo servidor front-end que no formaba parte del grupo anterior.

Los usuarios que tienen datos para archivar pueden sufrir pérdidas de datos hasta que se establezca una distribución estable del archivado para el grupo de servidores. Este período de posibles pérdidas de datos está limitado a 15 minutos para las conversaciones entre personas y a 30 minutos para las conferencias.

**Evitar**

Al realizar el mantenimiento, en lugar de iniciar los servidores front-end en el grupo de uno en uno, debe realizar una conmutación por error del grupo a otro grupo y, a continuación, realizar las tareas de mantenimiento en los servidores. También puede interrumpir el servicio antes de realizar las tareas de mantenimiento y luego restaurar su disponibilidad una vez completadas las tareas.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Los administradores no pueden obtener el número de licencias con el cmdlet Get-CsClientAccessLicense

**Emitir**

Los administradores no pueden obtener el uso exacto de licencias de cliente con el cmdlet **Get-CsClientAccessLicense**.

**Evitar**

Para comprobar el tipo de licencia del servidor, puede ejecutar el cmdlet **Get-CsService** para recuperar los nombres de dominio completos (FQDN) de todas las bases de datos. Si el FQDN del servidor front-end es el mismo que el FQDN de la base de datos back-end, la licencia es una licencia de Standard Edition. En caso contrario, la licencia será de un servidor Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>El número de licencias de cliente no se ha notificado con precisión

**Emitir**

Al determinar el número de licencias de cliente, es posible que se produzcan las siguientes condiciones:

1.  **Número impreciso de licencias para usuarios móviles**
    
    El número de licencias se basa en el número de direcciones IP únicas para los usuarios de dispositivos. El número de licencias estará limitado de las siguientes maneras:
    
      - El número de licencias será superior al real si la dirección IP del usuario se modifica durante las sesiones de Lync. Esto puede ocurrir cuando un usuario se conecta a Lync Server desde más de una ubicación con un cliente de escritorio.
    
      - El número de licencias será inferior al real si un usuario se conecta a un cliente móvil, ya que la dirección IP del dispositivo no se puede determinar.

2.  **Las licencias se cuentan dos veces para las llamadas de la red telefónica conmutada (RTC) al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync desviadas a las líneas RTC**
    
    En los siguientes escenarios, se contarán dos licencias adicionales en lugar de una, porque se considera tanto el número de teléfono como el usuario de Lync para determinar el número de licencias usadas. Para obtener datos precisos de las licencias, quite manualmente las licencias generadas por el número de teléfono.
    
      - Una llamada telefónica RTC a Lync
    
      - Una llamada de Lync a una línea RTC
    
      - Una llamada RTC a Lync y el posterior desvío de la llamada de Lync a una línea RTC. Se contará una de las líneas RTC.

3.  **No se contará ninguna licencia para un teléfono Lync conectado**
    
    Cuando un usuario usa un teléfono certificado para Lync, si el teléfono inicia sesión y permanece conectado, lo que conserva su estado de inicio de sesión, no se considerará que el teléfono usa una licencia si la consulta de las licencias se realiza después del inicio de sesión.

4.  **Licencias consideradas para teléfonos RTC que se unen a conferencias**
    
    Cuando un usuario se une a una conferencia con un teléfono RTC, se contará erróneamente una licencia por unirse a la conferencia. Sin embargo, no se necesita ninguna licencia para unirse a una conferencia con un teléfono RTC.

**Evitar**

1.  **Número impreciso de licencias para usuarios móviles**
    
      - Puede identificar manualmente las direcciones IP que pertenecen al mismo dispositivo y luego quitar una de ellas del número de licencias.
    
      - No existe ninguna solución para este problema con los dispositivos móviles que se conectan a un cliente de Lync.

2.  **Las licencias se cuentan dos veces para las llamadas RTC al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync desviadas a las líneas RTC**
    
    Deberá identificar manualmente el número de teléfono RTC y quitar el número de licencias generado para él.

3.  **No se contará ninguna licencia para un teléfono Lync conectado**
    
    Puede configurar el teléfono Lync para que cierre la sesión y vuelva a iniciarla, a un intervalo regular, por ejemplo, cada tres meses.

4.  **Licencias consideradas para teléfonos RTC que se unen a conferencias**
    
    Puede identificar manualmente el número de teléfono RTC que se usa para unirse a la conferencia y quitar la licencia generada por el número de teléfono.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>El panel de control de Lync Server deja de funcionar en un entorno VMware después de actualizar a Silverlight 5

**Emitir**

Si usa el panel de control de Lync Server en un entorno de VMware, el panel de control de Lync Server puede dejar de funcionar después de actualizar Microsoft Silverlight a la versión 5.

**Evitar**

Para solucionar este problema, siga uno de estos procedimientos:

  - Desinstalar Silverlight 5 e instalar Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).

  - Obtenga acceso al panel de control de Lync Server desde un equipo que no sea un equipo virtual VMware.
    
    Para ello, puede iniciar el panel de control de Lync Server desde el menú **Inicio** de Windows en el servidor, si las herramientas de administración de Lync Server están instaladas en el equipo.
    
    También puede obtener acceso al panel de control de Lync Server mediante un explorador Web. La dirección URL será similar a https://\<de\_grupo\_de\>servidores front-end de/CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>La información del usuario en el servicio de libreta de direcciones no se actualiza después de modificar el nombre distintivo del usuario en Active Directory

**Emitir**

Si se cambia el nombre distintivo de un usuario (también conocido como DN) en servicios de dominio de Active Directory, los cambios adicionales no se actualizarán en el servicio de libreta de direcciones (ABS). Esto no afecta el inicio de sesión ni la presencia del usuario, pero impedirá la comunicación del usuario si también se modifica la dirección SIP, ya que las búsquedas devolverán una dirección SIP obsoleta.

**Evitar**

Para solucionar este problema, no modifique el DN de un usuario. Si revierte el DN del usuario al valor anterior, las actualizaciones se reflejarán en el servicio de libreta de direcciones.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Instalación

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>El uso de caracteres que no sean ASCII puede dar lugar a que no se inicie Lync Server

**Emitir**

Se producirá un error en la instalación si el nombre de la carpeta de destino incluye caracteres que no sean ASCII (como Unicode, juego de caracteres de doble byte (DBCS), UTF-8 y UTF-16). Además, el programa de instalación puede tener éxito, pero el servidor no se iniciará si los caracteres que no son ASCII están incluidos en alguna de las siguientes opciones:

  - Nombre del equipo

  - Nombre de dominio

  - Nombre de usuario

  - URI del SIP del usuario

  - Nombre de la cuenta de servicio

**Evitar**

Use solo caracteres ASCII en el nombre de la carpeta de destino, el nombre del equipo, el nombre del dominio, el nombre de usuario, el URI del SIP del usuario y los nombres de cuenta de servicio.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>La revisión de "los daños en el montón se produce cuando un módulo llama al método al InsertEntityBody en IIS 7,5" debe estar instalado antes de instalar Lync Server 2013

**Emitir**

La revisión de "los daños en el montón se produce cuando un módulo llama al método al InsertEntityBody en[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)IIS 7,5" (), que se describe en[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)el artículo 264886 () de Microsoft Knowledge base, debe estar instalado antes de instalar Lync Server 2013.

**Evitar**

Descargue e instale la revisión desde el centro de descarga de [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft en.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 no se puede instalar en la versión de Windows Server 2012 OS RTM de ITA

**Emitir**

La instalación de Lync Server 2013 no funciona en ITA Windows Server 2012 debido a un error en la instalación de Windows fabric.

Se produce un error al instalar Windows Fabric porque se crean seguimientos de tejidos con el formato de hora HH:MM:SS. Sin embargo, en ITA Windows Server, el formato de hora es HH.MM.SS.

**Evitar**

Para solucionar este problema, actualice el registro del sistema antes de instalar Lync Server 2013. La clave del registro que debe actualizarse es: usuarios\_\\HKEY. Panel\\\\de control predeterminado\\sTimeFormat. Cambie el valor de sTimeFormat a HH: mm: SS mediante la interfaz de línea de comandos de Windows PowerShell como se indica a continuación:

1.  Inicie Windows PowerShell y ejecute los siguientes cmdlets:
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Para ver el valor actual, ejecute el siguiente cmdlet:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Anote el valor actual de sTimeFormat para poder restaurarlo una vez finalizada la instalación.

3.  Para establecer un nuevo valor, ejecute el siguiente cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Una vez instalado Lync Server 2013 correctamente, restaure el valor original de la sTimeFormat mediante la ejecución del siguiente cmdlet:
    
        - Set-ItemProperty $a-Name sTimeFormat-Value "<Value anotado en el paso 3. anterior> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Movilidad

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemas para clientes móviles durante el proceso de conmutación por error del servidor

**Emitir**

Cuando se produce un error en un Lync Server y se inicia el proceso de conmutación por error, los siguientes problemas pueden afectar a los usuarios de clientes móviles:

  - No se realiza ninguna llamada entrante de Lync ni señala hasta 10 minutos después de que se inicie la conmutación por error.

  - No se pueden aceptar las solicitudes entrantes de chat

  - No se pueden unir reuniones si el servidor con error es el servidor principal del usuario

**Evitar**

No existe ninguna solución para este problema. La funcionalidad normal se restaurará una vez que se haya completado el proceso de conmutación por error.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Si un usuario móvil rechaza una llamada entrante desde otro extremo de Lync, la llamada se muestra como una conversión perdida en clientes móviles de Lync

**Emitir**

Si un usuario móvil rechaza una llamada entrante y la llamada se originó en otro extremo de Lync, la llamada se muestra como una conversación perdida en el cliente móvil de Lync, en lugar de una llamada en la lista de llamadas de dispositivo.

**Evitar**

No existe ninguna solución para este problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Es posible que el cliente móvil no muestre el nombre para mostrar de un contacto federado al buscar contactos

**Emitir**

Es posible que el nombre para mostrar de los contactos federados no se muestre en algunos escenarios, como cuando se busca un contacto federado en la lista de contactos. Esto puede ocurrir cuando no hay ninguna suscripción de presencia activa para el contacto desde el cliente móvil de Lync.

**Evitar**

No existe ninguna solución para este problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>En el cliente móvil, la información de invite y timestamp no se encuentra en una conversación perdida que es una invitación a una conferencia

**Emitir**

En el cliente móvil, cuando una conversación perdida es una invitación a una conferencia, falta la información de la invitación y la marca de hora del mensaje de conversación perdido.

**Evitar**

No existe ninguna solución para este problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Los usuarios de clientes móviles que realizan llamadas mediante VoIP no pueden dejar correo de voz para los usuarios cuyo correo de voz está configurado en Exchange 2010 o versiones anteriores

**Emitir**

Si un usuario de cliente móvil usa VoIP para realizar llamadas, el usuario no podrá dejar mensajes de correo de voz para usuarios configurados para usar el correo de voz en Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.

**Evitar**

Para solucionar este problema, use Exchange 2010 con SP1 o una versión posterior de Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Cuando se usa Block con URL para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto

**Emitir**

Cuando se usa **Block con URL** para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto cuando la versión de cliente no es compatible.

**Evitar**

Para solucionar este problema, configure la versión de cliente para que use **Block** en lugar de **Block with URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conferencia

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>El software antivirus que se ejecuta en los servidores front-end de Lync Server 2013 puede provocar el reciclaje del dominio de aplicación, lo que interrumpe temporalmente el servicio para los clientes de Lync Mobile App 2013, Lync Mobile 2010 y Lync Mobile 2013

**Emitir**

El software antivirus puede desencadenar reinicios de dominio de aplicación, lo que puede dar como resultado aplicaciones de cliente de la API Web de Lync Mobility Service 2013 y comunicaciones unificadas (UC) (Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013) para perder su estado.

**Evitar**

Para solucionar este problema, excluya las carpetas que contienen componentes web y .NET Framework del análisis antivirus. Para obtener más información, consulte el artículo 312592 de Microsoft Knowledge base, "PRB: Random Application restarts with ' Application is reiniciating ' error en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)ASP.net, en.

Se deben excluir las siguientes carpetas:

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\Ucwa int

  - % ProgramFiles%\\de componentes\\\\Web de Microsoft Lync Server\\2013 de Ucwa ext

  - % WINDIR%\\Microsoft.net\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Los controles ActiveX o la compatibilidad con XMLHTTP nativo deben estar habilitados en Windows Internet Explorer para unirse correctamente a las conferencias.

**Emitir**

Si un usuario deshabilitó los controles ActiveX y la compatibilidad con XMLHTTP nativo en la configuración del explorador Windows Internet Explorer, el usuario no podrá unirse a una reunión si se seleccionó Internet Explorer como explorador predeterminado.

**Evitar**

Habilite los controles ActiveX o la compatibilidad con XMLHTTP nativo en Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>El servicio de conferencia Web de Lync Server no puede recuperarse del modo crítico

**Emitir**

Si el modo crítico está activado para el archivado, en caso de errores del sistema, se iniciará el modo crítico y las conferencias ya no funcionarán para los participantes. Una vez que el administrador corrige los errores del sistema (por ejemplo, un problema en la base de datos), el servicio de conferencia de datos no se recupera de manera automática, y el administrador debe reiniciar el servicio manualmente para reanudar las conferencias.

**Evitar**

El administrador debe reiniciar manualmente el servicio de conferencia una vez que se corrige el error del sistema.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>El servicio de conferencia web omite el proxy HTTP para los servidores externos de Office Web App

**Emitir**

Si ha implementado un servidor de Office Web Apps externo al servicio de conferencia web (es decir, un servidor que no está en la red corporativa interna) en Internet, la red perimetral y el servicio de conferencia web necesita un proxy HTTP para conectarse a este, el Se producirá un error en la detección del servidor de Office Web Apps. El servicio de conferencia web ignora la configuración de proxy HTTP, tal como se define en Topology Builder for Office Web Apps Server Setup. Como resultado, el cliente de Lync no podrá compartir Microsoft PowerPoint 2010 con otros participantes en la Conferencia. Si está instalando Lync Server local y también configura Office Web Apps Server local en la red interna, no se requiere una configuración de proxy.

**Evitar**

La única solución alternativa es no tener una configuración de implementación que requiera el uso de proxy HTTP para comunicarse con un servidor de Office Web Apps externo.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>No se admite Agregar vídeo a una conferencia de un proveedor de servicios de audioconferencia

**Emitir**

No es posible agregar un vídeo si el usuario se unió a una conferencia de un proveedor de servicios de audioconferencia.

**Evitar**

No existe ninguna solución para este problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologías con IPv6 habilitada fuerce la actualización automática del complemento Silverlight Web App Silverlight para garantizar que la funcionalidad de uso compartido de la pantalla puede funcionar desde Lync Web App

**Emitir**

Cuando se configura una topología con IPv6 habilitado, los usuarios no pueden compartir su pantalla desde el cliente de Lync Web App si ya hay instalada una versión anterior del complemento de uso compartido de la pantalla.

**Evitar**

Para forzar una actualización a la versión más reciente del complemento de uso compartido de pantalla al unirse a una reunión a través de Lync Web App, modifique el valor de **MinSupportedBuildVersion** de "4.0.7457.0" a "4.0.7577.380" en los dos archivos siguientes:

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\int\\Client plugins\\ReachAppShPluginProperties. XML

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\complementos de cliente\\ext\\ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>En algunos casos, es posible que un cliente de Lync que se ejecuta en un equipo configurado para usar IPv4 e IPv6 Dual Stack no admita funciones basadas en la subred IP del equipo, como E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en ubicación.

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

**Emitir**

Cuando un cliente de Lync se ejecuta en un equipo que está habilitado para la pila dual IPv4 e IPv6 y se basa en la resolución DNS del servidor proxy, el cliente puede usar la dirección IPv6 del equipo para iniciar sesión. Después de hacerlo, el cliente de Lync será compatible solo con las funciones compatibles con IPv6, que excluyen el enrutamiento basado en la E911, la omisión de medios, el control de admisión de llamadas y la ubicación.

**Evitar**

Para solucionar este problema, deshabilite la compatibilidad de IPv6 en el equipo cliente.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Si la telefonía IP empresarial no está configurada para un usuario, el usuario tendrá que usar el formato E164 para realizar llamadas desde una conferencia.

**Emitir**

Si la telefonía IP empresarial no está configurada para un usuario, dicho usuario tendrá que usar el formato E164 para marcar correctamente desde una conferencia. Si no se usa el formato E164, el usuario no podrá realizar llamadas salientes desde la conferencia.

**Evitar**

Para solucionar este problema, los usuarios que no están habilitados para telefonía IP empresarial deben marcar desde una conferencia con números en el formato E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Presencia

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería

**Emitir**

Si un usuario seleccionó "Bloquear todas las invitaciones y comunicaciones" cuando el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería.

**Evitar**

Para solucionar este problema, puede desactivar el almacén de contactos unificado para el usuario. Para ello, ejecute los siguientes cmdlets:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Por ejemplo:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Los usuarios de Office Communications Server 2007 R2 hospedados de forma local no pueden ver el estado de presencia de los usuarios de Skype empresarial online en implementaciones híbridas: híbrida

**Emitir**

El problema puede producirse en una implementación híbrida cuando se usa un director 2013 de Lync Server.

El estado de presencia de los usuarios hospedados en Skype empresarial online se muestra como presencia desconocida para los usuarios locales. Además, los usuarios hospedados en Skype empresarial online no pueden ver el estado de presencia de los usuarios locales de Office Communications Server R2.

**Evitar**

Para evitar este problema parcialmente, cambie el servidor principal (msRTCSIP-presencehomeserver) de los usuarios de Skype empresarial online para que apunte a un grupo local de Lync Server 2013 en lugar del Director de Lync Server 2013. Puede modificar esta configuración en el servidor front-end local.

Esta solución mostrará correctamente el estado de presencia de los usuarios hospedados en Office Communications Server 2007 R2 a los usuarios de Skype empresarial online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas y recogida de llamadas grupales

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Una persona que llama puede oír un segundo de la música en espera durante el establecimiento de una llamada con la entidad de recuperación

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

**Emitir**

Cuando se recupera una llamada a través de la atención de llamadas grupales, el autor de la llamada puede oír un segundo de la música en espera durante el establecimiento de la llamada con la parte del recuperador.

**Evitar**

No existe ninguna solución para este problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agente de grupo de respuesta puede iniciar sesión y cerrar sesión mediante una consola de agente 2010 de Lync Server para Lync Server 2010 solo a grupos de agentes formales.

**Emitir**

Un agente de grupo de respuesta 2013 de Lync Server puede iniciar y cerrar sesión con una consola de agente de Lync Server 2010 solamente para los grupos de agentes formales de Lync Server 2010. En la consola del agente 2010 de Lync Server, los usuarios solo pueden ver el grupo de respuesta de Lync Server 2010 al que pertenecen. No pueden ver ninguno de los grupos de respuesta 2013 de Lync Server a los que pertenecen.

**Evitar**

Si el agente de grupo de respuesta es un usuario de Lync Server 2013 y parte de un grupo de agentes formales de Lync Server 2013, el usuario debe tener acceso a la consola del agente de Lync Server 2013 directamente a través de un vínculo Web en un explorador para iniciar sesión y cerrar los grupos de agentes de Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agente de grupo de respuesta 2010 de Lync Server no puede realizar llamadas en nombre de un grupo de respuesta de Lync Server 2013

**Emitir**

Un usuario de Lync Server 2010 que es un agente de un grupo de respuesta de Lync Server 2013 no puede realizar una llamada en nombre del grupo de respuesta. El grupo de respuesta de Lync Server 2013 no estará disponible en el cliente de Lync para realizar una llamada.

**Evitar**

Para solucionar este problema, debe mover el usuario de Lync Server 2010 a Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>La eliminación de un grupo de respuesta de Lync Server 2010 después de que se haya migrado a Lync Server 2013 impedirá que el grupo de respuesta acepte llamadas entrantes

**Emitir**

Si un grupo de respuesta que se ha migrado de Lync Server 2010 a Lync Server 2013 se ha quitado de Lync Server 2010 a través del panel de control de Lync Server o el shell de administración de Lync Server, el grupo de respuesta de Lync Server 2013 dejará de recibir las llamadas entrantes.

**Evitar**

Para solucionar este problema, no quite los grupos de respuesta de Lync Server 2010 que se hayan migrado de Lync Server 2010 a Lync Server 2013.

Si ya se ha quitado el grupo de respuesta, debe volver a implementarlo en Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Cuando un nuevo flujo de trabajo administrado se establece en inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo

**Emitir**

Cuando un nuevo flujo de trabajo administrado se establece en inactivo al crearse, se producirá un error al implementar el flujo de trabajo. Este problema se detecta cuando el flujo de trabajo se establece en inactivo al crearse, pero no afecta a un flujo de trabajo que se modifica para establecerse en inactivo después de su implementación.

**Evitar**

Al crear e implementar un flujo de trabajo, establezca el flujo de trabajo como activo y luego impleméntelo. Una vez que se implementa correctamente, el flujo de trabajo se puede modificar y establecer en inactivo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>La eliminación de un grupo de respuesta del grupo de propietarios impedirá que el grupo de respuesta del grupo de copia de seguridad acepte llamadas entrantes durante la conmutación por error si el grupo de respuesta se ha importado al grupo de copia de seguridad

**Emitir**

Si un grupo de respuesta que pertenece al grupo principal se ha importado al grupo de copia de seguridad sin sobrescribir el propietario y el grupo de respuesta se quita del grupo de servidores propietario, el grupo de respuesta del grupo de copia de seguridad no aceptará ninguna llamada entrante durante la conmutación por error.

**Evitar**

Tendrá que volver a implementar el grupo de respuesta en el grupo principal. A continuación, tendrá que exportar la configuración del grupo de respuesta del grupo principal e importarla nuevamente en el grupo de copia de seguridad.

También puede volver a crear el grupo de respuesta en el grupo de copia de seguridad. En este caso, el grupo de copia de seguridad será el grupo propietario del grupo de respuesta.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>No se puede recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas si la solicitud de recuperación se realiza en nombre de un grupo de respuesta

**Emitir**

Cuando se cumplen las siguientes condiciones, se producirá un error en la solicitud de recuperación de una llamada estacionada:

  - Un agente forma parte de un grupo de respuesta anónimo

  - El agente intenta recuperar una llamada estacionada de la aplicación estacionamiento de llamadas a través del grupo de respuesta anónimo

  - El agente intenta recuperar la llamada marcando el número de órbita con la opción de llamada en nombre de un grupo de respuesta o con la misma opción en el cliente de Lync Attendant

**Evitar**

No existen soluciones para este problema. La llamada estacionada debe recuperarse sin hacerlo en nombre de un grupo de respuesta.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Panel de control de Lync Server, Generador de topologías y Herramienta de planeación

<div>

## <a name="planning-tool-limitations"></a>Limitaciones de la herramienta de planeación

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

**Emitir**

La herramienta de planeación tiene las siguientes limitaciones al planear la implementación:

  - Hay un máximo de 10 sitios centrales admitidos

  - Cada sitio central puede tener un máximo de 14 sitios de sucursal

  - Cada sitio central puede tener un máximo de 240.000 usuarios

Además, la herramienta de planeación no incluye los valores de los siguientes elementos al calcular la topología recomendada:

  - El número de usuarios que están hospedados en línea

  - El porcentaje de usuarios que están habilitados para la Federación XMPP

  - Porcentaje de usuarios que usan Lync Web App

**Evitar**

No hay ninguna solución alternativa para estos problemas. Para obtener más información acerca de la herramienta de planeación, consulte [diseño de la topología para Lync Server 2013 mediante la herramienta de planeación](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Es posible que la herramienta de planeación no use direcciones IP definidas previamente para la red perimetral al actualizar las opciones

**Emitir**

Una vez que haya completado el diseño mediante la herramienta de planeación, si realiza cambios en las opciones de la red perimetral, se pueden agregar direcciones IP adicionales al diseño en lugar de actualizar las direcciones IP existentes. Esto puede ocurrir cuando se ven los detalles del diagrama de red perimetral, seleccione **hacer clic aquí para actualizar las opciones**y, a continuación, en el cuadro de diálogo Opciones de configuración, seleccione red perimetral, seleccione **quiero usar los mismos FQDN y direcciones IP, pero distintos puertos para los servicios perimetrales en el servidor perimetral**. Aplicar los cambios puede dar lugar a que se agreguen nuevas direcciones IP y servidores perimetrales al diseño.

**Evitar**

No hay ninguna solución alternativa para este problema en este momento.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>En el panel de control de Lync Server, "mover todos los usuarios al grupo" puede que no funcione según lo esperado

**Emitir**

Cuando se usa el panel de control de Lync Server para mover todos los usuarios de un grupo a otro en un entorno complejo de Active Directory, como uno con varios controladores de dominio y dominios principales/secundarios, se puede devolver un mensaje de error que indica que "el usuario especificado no es un usuario heredado; use el cmdlet Move-CsUser en su lugar". Esto es resultado de tiempos de replicación más largos en entornos complejos de Active Directory.

**Evitar**

Para solucionar este problema, siga uno de estos procedimientos:

  - Use filtros en el panel de control de Lync Server para buscar usuarios heredados, seleccione esos usuarios y, a continuación, use el **comando mover usuarios seleccionados a grupo** en lugar de **mover todos los usuarios al grupo**.

  - Use el shell de administración de Lync Server para mover usuarios heredados en lotes con los cmdlets de Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>El panel de control de Lync Server deja de funcionar en un entorno de VMware después de que el complemento de explorador Microsoft Silverlight se actualice a la versión 5

**Emitir**

Si usa el panel de control de Lync Server en un entorno de VMware, el panel de control de Lync Server puede dejar de funcionar después de actualizar Silverlight a la versión 5.

**Evitar**

Para solucionar este problema, siga uno de estos procedimientos:

  - Desinstale Silverlight 5 y luego instale Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).

  - Abra el panel de control de Lync Server desde un equipo que no sea un equipo virtual VMware.
    
    Para abrir el panel de control de Lync Server desde un equipo remoto, instale las herramientas de administración de Lync Server en el equipo y, a continuación, inicie el panel de control de Lync Server desde el menú **Inicio** de Windows.
    
    También puede abrir el panel de control de Lync Server escribiendo la dirección URL en un explorador Web. La dirección URL será similar a https://\<de\_grupo\_de\>servidores front-end de/CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un administrador no puede ejecutar el cmdlet Uninstall-csMirrorDB después de quitar la base de datos de reflejo en el generador de topologías.

**Emitir**

Cuando un administrador deshabilita una base de datos de reflejo en el generador de topologías y elimina la base de datos de reflejo en el generador de topologías, se muestra un mensaje en la lista de tareas pendientes para que el administrador ejecute el cmdlet **Uninstall-csMirrorDatabase** para quitar la creación de reflejo de SQL Server. Cuando el administrador intenta ejecutar el cmdlet, se produce un error.

**Evitar**

Para quitar la creación de reflejos de SQL de un grupo en el generador de topologías, primero debe usar un cmdlet para quitar el reflejo en SQL Server. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por ejemplo, para quitar el reflejo y descartar las bases de datos de usuario, escriba lo siguiente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

El parámetro *DropExistingDatabasesOnMirror* hace que las bases de datos afectadas se eliminen del reflejo. Después, para quitar el reflejo de la topología, haga lo siguiente:

1.  En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.

2.  Desactive **Habilitar creación de reflejo de almacén SQL** y haga clic en **Aceptar**.

3.  Publique la topología.

<div class="">


> [!IMPORTANT]  
> Siempre que realice un cambio en una relación de creación de reflejo de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Los errores de validación se devuelven en el generador de topologías cuando un administrador intenta quitar una implementación con un grupo de servidores front-end que tiene un almacén de testigos asociado

**Emitir**

Si un administrador intenta usar el comando **quitar implementación** en el generador de topologías para quitar una implementación que incluye un grupo de servidores front-end con un almacén de testigos asociado, se muestra un error de validación en el generador de topologías y la acción no se llevará a cabo.

**Evitar**

Para solucionar este problema, siga uno de estos procedimientos:

  - Quite el almacén de testigos antes de tratar de quitar la implementación.

  - Agregue un almacén de testigos para el grupo de servidores front-end y luego quítelo.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>La información de implementación del servidor de chat persistente es incoherente entre la herramienta de planeación y el generador de topologías

**Emitir**

Cuando la herramienta de planeación de Lync Server 2013 da como resultado el diagrama de topología de sitio para una implementación de servidor de chat persistente con recuperación ante desastres habilitada, el diagrama de topologías de sitio incluye varios sitios (físicos), con servidores de chat persistentes asignados uniformemente en cada emplaza. En el generador de topologías, todos los servidores de chat persistente se representan como pertenecientes a un sitio único (lógico) y se enumeran en el mismo nodo de grupo de servidores de chat persistente.

**Evitar**

Actualmente, no existe ninguna solución para este problema. El usuario debe analizar el resultado de la herramienta de planeación de la implementación del servidor de chat persistente y modificar el plan para satisfacer sus necesidades específicas.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localización

<div>

## <a name="monitoring"></a>Supervisión

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>El Asistente para implementar informes de supervisión muestra caracteres incorrectos en determinadas circunstancias al usar la versión de Asia oriental de Lync Server

**Emitir**

Cuando se usa una versión de Asia oriental de Lync Server 2013 (por ejemplo, Chino (simplificado), Chino (tradicional), Japonés o coreano, en un sistema operativo que tiene la configuración regional del sistema no establecida en un idioma del este asiático, el Asistente para implementar informes de supervisión mostrar signos de interrogación u otros caracteres en lugar de mensajes localizados.

**Evitar**

Para solucionar este problema, establezca la configuración regional del sistema operativo y Lync Server 2013 en el mismo idioma, que mostrará todos los mensajes correctamente.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Panel de Control de Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>En algunos casos, el primer elemento de la barra de navegación superior de una página del panel de control de Lync Server desaparece cuando se hace clic en el último elemento de la barra de navegación superior

**Emitir**

Hay tres casos conocidos en los que, al hacer clic en el último elemento de la barra de navegación superior de una página del panel de control de Lync Server, el primer elemento de la barra de navegación superior desaparecerá:

  - En la versión en francés, en la página "Féderation et accès externe", desaparece el elemento "Stratégie d'accès externe" al hacer clic en "Partenaires fédérés XMPP".

  - En la versión en alemán, en la página "Clients", desaparece el elemento "Clientversionskonfiguration" al hacer clic en "Pushbenachrichtigungskonfiguration".

  - En la versión en ruso, en la página "Конфигурация сети", desaparece el elemento "Глобально" al hacer clic en "Маршрут региона".

**Evitar**

Para solucionar este problema, actualice la página del panel de control de Lync Server en el explorador. La página se cargará en el explorador con todos los elementos de la barra de navegación superior visibles.

</div>

</div>

<div>

## <a name="address-book"></a>Libreta de direcciones

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>La indización de la libreta de direcciones no funciona según lo esperado en algunos idiomas

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

Si las propiedades de un usuario contienen un campo indizado y ese campo contiene solo caracteres que no se pueden indizar, el usuario no aparecerá en las búsquedas realizadas en la libreta de direcciones.

Los siguientes caracteres y configuraciones regionales no se pueden indizar:

  - Caracteres en mayúsculas: cirílico, griego y armenio

  - Caracteres en mayúsculas acentuados

  - Tailandés

  - Lao

  - Myanmar

  - Devanagari

  - Etíope

  - Tibetano

  - Bengalí

  - Gujarati

  - Telugu

  - Todos los demás scripts indios

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, programador web y componentes Web

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Reserva de idioma para determinados idiomas en el programador web de Lync, el acceso telefónico, el iniciador de sesiones, la administración del salón de chat persistente y OCTab podrían no funcionar según lo esperado

**Emitir**

Al seleccionar una configuración regional neutra en un explorador Web (en Internet Explorer, por ejemplo, el nombre del idioma sin especificación adicional, como " \[noruego\]no") en lugar de una configuración regional que especifica el idioma, el script y la configuración regional (como "noruego, Bokmål \[(Noruega)\]NB-no") puede llevar a un comportamiento de visualización inesperado para determinados idiomas en el programador web de Lync, acceso telefónico, iniciador de chat, administración de salones de Por ejemplo, es posible que los usuarios vean la página en inglés al seleccionar uno de los siguientes idiomas:

  - Noruego

  - Portugués

  - Serbio

**Evitar**

Si desea seleccionar un idioma con una configuración regional neutral, asegúrese siempre de agregar también el idioma con una configuración regional específica (con un script o código de país) como idioma adicional en la lista de preferencias de idioma del explorador.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Hay compatibilidad limitada con las configuraciones regionales azerí y uzbeko al usar el programador web de Lync, el acceso telefónico, el iniciador de reuniones, la administración del salón de chat persistente y OCTab en algunos exploradores Web

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

**Emitir**

Cuando usa Internet Explorer 8 o Internet Explorer 9 y establece el idioma del explorador en Azerí (Latino) o uzbeko (Latino), las páginas de acceso telefónico local y de iniciador de participación se mostrarán en inglés o en el idioma preferido establecido en el explorador.

Al usar los exploradores de Firefox o Chrome y establecer el idioma del explorador en Azerí (Latino) o uzbeko (Latino), la aplicación Web de Lync, el programador web de Lync y el OCTab de RGS se mostrarán en inglés o en el idioma preferido establecido para el explorador.

La configuración regional uzbeko (Latín) no es compatible con el explorador Safari.

**Evitar**

No hay ninguna solución alternativa para estos problemas.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>Falta la flecha de la lista desplegable para "unirse a la reunión de" en la versión en rumano de Lync Web App

**Emitir**

Cuando un usuario que usa la versión rumano de Lync Web App realiza los pasos siguientes, la flecha desplegable no se muestra para unirse a la **reunión** en la lista desplegable:

1.  Seleccione **Recordar mis datos en este equipo** en la pestaña **General**.

2.  Seleccione la pestaña **Teléfono**.

3.  Haga clic en la lista desplegable para **Unirse a la reunión**.
    
    Los usuarios no verán una flecha que indica que hay más opciones que las predeterminadas de **Lync Web App**, entre las que se incluyen: **no Únase a audio** (en rumano, "nu se valores la aplicación audio") y un **número nuevo**"(en rumano," Număr Nou ").

**Evitar**

Aunque no se muestre la flecha de esta lista desplegable, los usuarios pueden seleccionar de todos modos las opciones adicionales de la lista haciendo clic en el valor predeterminado.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Cuando se usa la versión en Turco del programador web de Lync, no se puede guardar una reunión al usar la opción "las personas que elijan" en "quién es un moderador"

**Emitir**

Al crear o modificar una reunión en la versión en turco del Programador web de Lync, no se admite la opción "Las personas que yo elija" en "Quién es moderador". Cuando se selecciona esta opción, no se puede guardar la reunión. En cambio, aparece un mensaje de error que indica que una o más personas no pueden convertirse en moderadores.

**Evitar**

Para solucionar este problema, los usuarios pueden usar la opción predeterminada "Personas de mi compañía" o cualquier otra opción, como "Solo el organizador" o "Todos, incluidas las personas de fuera de mi compañía". El organizador puede disminuir o aumentar el nivel de los participantes para establecer sus roles correctos más adelante, una vez que se hayan unido a la reunión.

Además, los usuarios que entienden otro idioma pueden cambiar la selección de idioma en el explorador. Pueden elegir uno de los otros 43 idiomas admitidos e intentar usar la opción "Las personas que yo elija".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Este documento hace referencia a una versión preliminar de un producto de software que puede haber cambiado considerablemente antes del lanzamiento de la versión comercial definitiva. La información que contiene es propiedad confidencial de Microsoft Corporation. Dicha información se divulga conforme a un acuerdo de confidencialidad entre el destinatario y Microsoft. Este documento se proporciona con carácter informativo únicamente y Microsoft no otorga garantías expresas ni implícitas en él. La información contenida en este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a modificaciones sin previo aviso. El usuario asume todos los riesgos resultantes del uso de este documento. A menos que se indique lo contrario, las compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares y eventos mencionados en los ejemplos son ficticios. No se pretende indicar ni debe deducirse ninguna asociación con compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares o eventos reales. El cumplimiento de las leyes de derechos de autor aplicables es responsabilidad del usuario. Sin limitar los derechos de autor, ninguna parte de este documento puede ser reproducida, almacenada o introducida en un sistema de recuperación, ni transmitida, de ninguna forma ni por ningún medio (ya sea electrónico, mecánico, fotocopia, grabación o de otro tipo), con ningún propósito, sin autorización expresa y por escrito de Microsoft Corporation.

Microsoft puede ser propietario de patentes, solicitudes de patentes, marcas comerciales, derechos de autor u otros derechos de propiedad intelectual relacionados con el tema de este documento. Excepto cuando quede expresamente indicado en cualquier contrato de licencia de Microsoft, el suministro de este documento no le otorga ninguna licencia sobre dichas patentes, marcas comerciales, derechos de autor u otro tipo de propiedad intelectual.

© 2012 Microsoft Corporation. Todos los derechos reservados.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook y SQL Server son marcas comerciales o marcas registradas de Microsoft Corporation en los Estados Unidos y/o en otros países o regiones.

Todas las demás marcas comerciales pertenecen a sus respectivos propietarios.

</div>

</div>

<span> </span>

</div>

</div>

</div>

