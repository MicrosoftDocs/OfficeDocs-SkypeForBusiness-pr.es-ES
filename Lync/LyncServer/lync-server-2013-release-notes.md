---
title: 'Lync Server 2013: Notas de la versión'
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
ms.openlocfilehash: 10961f0a8e59fe1d0dc0268b430f37fd294252b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Notas de la versión de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

Bienvenido a las notas de la versión de Lync Server 2013. Consulte este archivo para obtener información sobre los problemas conocidos de Lync Server 2013.

<div>

## <a name="about-this-document"></a>Acerca de este documento

Este documento contiene información importante que debe conocer antes de implementar y usar Lync Server 2013. Para obtener más información sobre Lync Server 2013, consulte la documentación de [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

Este documento contiene las secciones siguientes:

  - Cliente de Lync 2013

  - Lync Server

  - Instalación

  - Movilidad

  - Conferencias

  - Telefonía IP empresarial

  - Presence

  - Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

  - Panel de control de Lync Server, Generador de topologías y Herramienta de planeación

  - Local

  - Tratados

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Cliente de Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>La transferencia de un archivo en un mensaje instantáneo da error si el archivo está abierto en otra aplicación

**Vulnerabilidad**

Si intenta transferir un archivo, como un documento de Word, incluyendo en un mensaje instantáneo a otro usuario de Lync, la transferencia parecerá que se realizará correctamente, pero es posible que no se pueda transferir el archivo. Se mostrará un icono para el tipo de archivo en el cliente de Lync, pero el destinatario no podrá abrir el archivo. No se muestra ningún mensaje de error para informarle que la transferencia no se realizó correctamente.

**Solución alternativa**

Para evitar este problema, cierre el archivo abierto o la aplicación que lo tiene abierto antes de intentar transferir el archivo en un mensaje instantáneo.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Si se produce un error en la replicación de datos del servicio de almacenamiento de Lync Server, los administradores deberán comprobar los contadores de rendimiento de los elementos de cola del servicio de almacenamiento obsoleto

**Vulnerabilidad**

El servicio de almacenamiento de Lync Server usa Windows fabric para la replicación. Si se eliminan datos en un servidor front-end principal, pero se produce un error en la eliminación en un servidor de front-end secundario (por ejemplo, si hay un apagado inesperado o un error en el servidor front-end), los datos se pueden dejar atrás y "huérfanos". Los datos huérfanos pueden hacer que el rendimiento se degrade y desperdicie espacio en la unidad.

**Solución alternativa**

Para evitar este problema, si se generan los eventos\_LYSS\_dB\_Space\_use error (ID = 32058) y\_LYSS\_dB\_Space\_use Critical (ID = 32059) en el registro de eventos, los administradores deben comprobar el contador de rendimiento en el servidor front-end en **LS: LYSS, API de servicio de almacenamiento** con el nombre **LYSS-número actual de elementos de cola obsoletos del servicio de almacenamiento**. Si este contador de rendimiento tiene un valor alto (por ejemplo, mayor que 50000), el administrador debe ejecutar la herramienta CleanuUpStorageServiceData. exe del kit de recursos de Lync Server 2013, que eliminará todos los datos huérfanos del grupo. Para obtener más información sobre la herramienta, consulte la documentación del kit de recursos de Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Cada vez que se cambie la configuración de la dirección IP de un servidor o grupo, es necesario reiniciar los servicios de Lync Server.

**Vulnerabilidad**

Cuando se cambia la configuración de la dirección IP en una implementación de Lync Server 2013, por ejemplo, al cambiar de IPv4 a pila dual o de pila doble a IPv6, no todos los componentes del servidor recogen el cambio de configuración hasta que se reinicien los servicios.

**Solución alternativa**

Para solucionar este problema, reinicie los servicios de Lync Server después de cambiar la configuración de la dirección IP de la implementación. Para ello, ejecute los siguientes cmdlets en el shell de administración de Lync Server:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>El cmdlet de la transacción sintética de las conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013

**Vulnerabilidad**

El cmdlet **Test-CsDialInConferencing** de la transacción sintética de conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013.

**Solución alternativa**

El uso del cmdlet de transacciones sintéticas de las conferencias de acceso telefónico local **prueba-CsDialInConferencing** es compatible solamente internamente con una empresa.

Los administradores pueden continuar usando el cmdlet en el shell de administración de Lync Server para la solución de problemas. Si es necesario, una empresa también puede desarrollar un paquete de administración privado para ejecutar el cmdlet de forma interna.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>El servicio de registro centralizado se detiene si el tráfico de red se interrumpe cuando los archivos de registro se copian en un recurso compartido de red

**Vulnerabilidad**

Cuando el servicio de registro centralizado está configurado para usar una ruta de acceso de red (el valor del parámetro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** es una ruta de acceso UNC válida), los archivos de registro en caché se copian en el recurso compartido de red. Si se produce una interrupción en el tráfico de red mientras se copian los archivos, se producirá una excepción que hará que el servicio de registro centralizado se detenga.

El servicio está configurado para reiniciarse automáticamente hasta tres veces, de modo que el servicio se recupere de las tres primeras excepciones.

**Solución alternativa**

No hay ninguna solución para este problema. Para identificar el problema, supervise el registro de eventos para el identificador de evento 7031 del "Administrador de control de servicios" que registra cuando el servicio "agente de servicios de registro centralizado de Lync Server" ha finalizado inesperadamente. Si esto sucede más de tres veces, reinicie el servicio de forma manual con el cmdlet **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Los elementos de la cola del servicio de almacenamiento necesitan importarse manualmente

**Vulnerabilidad**

Lync Server 2013 almacena datos sobre las conferencias y la mensajería instantánea, como los mensajes archivados y la grabación de detalles de llamadas (CDR), en una base de datos en cada servidor front-end. Los datos se almacenan en la base de datos mientras se procesan antes de enviarse al destino previsto. Para mejorar el rendimiento, Lync Server 2013 exporta periódicamente los elementos de cola de la base de datos local que no se procesan durante un período de tiempo prolongado y los guarda en el almacén de archivos. Si el almacén de archivos no está disponible, los elementos se almacenan en cada servidor front-end. Se produce la misma operación para evitar la pérdida de datos durante la conmutación por error de la agrupación.

Durante la operación de exportación, el servicio de almacenamiento de Lync Server registra cada una de las fases en el registro de eventos con los identificadores de evento de 32075 (inicio completo), 32076 (vaciado completo), 32082 (se inicia el nivel de mantenimiento), 32083 (volcado de nivel de mantenimiento se ha completado), 32089 (vaciado debido a rellenando la base de datos). Estos datos no se volverán a importar automáticamente al sistema para ser procesados y enviados a su destino final (SQL Server o Exchange Server).

**Solución alternativa**

Para importar los datos en el sistema, los administradores deberán usar la herramienta ImportStorageServiceData del kit de recursos de Lync Server, que agregará los datos al sistema para ser procesados y enviados a su destino final.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Se producirá un error en las búsquedas en la libreta de direcciones web de libreta de direcciones si el valor predeterminado de UseNormalizationRules cambia a false.

**Vulnerabilidad**

Si el valor predeterminado de UseNormalizationRules se cambia a false, las búsquedas en la libreta de direcciones web no se realizarán correctamente. Una vez que se cambie el valor predeterminado, los usuarios del cliente de Lync no podrán usar la consulta Web de la libreta de direcciones de Lync para buscar usuarios.

**Solución alternativa**

Si el valor predeterminado de UseNormalizationRules se establece en false para que los usuarios puedan usar números de teléfono definidos en los servicios de dominio de Active Directory sin Lync Server 2013 aplicando reglas de normalización, haga lo siguiente para solucionar este problema:

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Siga uno de estos pasos:
    
      - Si su implementación solo incluye servidores de Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de UseNormalizationRules y IgnoreGenericRules a true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere a que se produzca la replicación de CMS en todos los grupos.

4.  Modifique el archivo de reglas de normalización de teléfonos de su implementación para borrar el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Lync Server 2013. Si el archivo no está presente, cree un archivo vacío denominado "regla de\_\_normalización\_\_de número de teléfono de la empresa. txt".

5.  Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de su implementación.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>El evento de error del servidor de la libreta de direcciones 21054 se genera una vez al día para cada grupo de Lync 2013

**Vulnerabilidad**

El servidor de la libreta de direcciones de Lync Server 2013 generará el evento de error 21054 una vez al día al realizar el mantenimiento diario. El error también se genera cada vez que un administrador ejecuta el cmdlet **Update-csAddressBook** , incluso cuando la actualización se realiza correctamente. Sin embargo, este evento de error puede ignorarse con seguridad cuando la actualización se realice correctamente.

**Solución alternativa**

Cuando encuentre este evento de error, ejecute el siguiente cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si el cmdlet informa de que no hay objetos no indizados ni abandonados, se puede ignorar el evento de error 21054.

Además, el indicador de mantenimiento de clave (KHI) "los usuarios de la libreta de direcciones correctamente indizados" deberían estar desactivados en System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Las solicitudes pueden fallar cuando se configura IPv6 en un grupo de servidores perimetrales

**Vulnerabilidad**

Cuando se configura IPv6 en un grupo Edge, algunas solicitudes al grupo perimetral pueden fallar.

**Solución alternativa**

Para solucionar este problema, no configure un grupo perimetral con IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>El cmdlet Invoke-csPoolFailback puede fallar durante la conmutación por recuperación del grupo

**Vulnerabilidad**

Al intentar devolver un grupo por error, el cmdlet **Invoke-csPoolFailback** puede dar el error "no se pudo completar el proceso de hidratación tras un intento repetido".

**Solución alternativa**

Para solucionar este problema, ejecute el cmdlet de nuevo y espere hasta que el cmdlet se complete correctamente. Tenga en cuenta que el proceso de conmutación por recuperación puede demorar varios minutos en completarse. Una agrupación con usuarios de 20.000 puede tardar hasta 60 minutos.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Se pueden perder datos al agregar un servidor front-end a un grupo ya establecido: híbrido, Skype empresarial online

**Vulnerabilidad**

Puede encontrarse este problema en un entorno en el que un grupo tiene más de un servidor front-end y se puede reiniciar uno de los servidores front-end o agregar un nuevo servidor front-end que no fuera parte del grupo.

Los usuarios cuyos datos se estén archivados pueden experimentar pérdida de datos hasta que se haya establecido una distribución estable del archivado de datos para el grupo. Este período de pérdida potencial de datos se limita a 15 minutos para las conversaciones entre personas y 30 minutos para las conferencias.

**Solución alternativa**

Al realizar el mantenimiento, en lugar de iniciar servidores front-end en el grupo uno por uno, debe realizar la conmutación por error del grupo a otro grupo y, a continuación, realizar tareas de mantenimiento en los servidores. También puede hacer que el servicio no esté disponible antes de realizar tareas de mantenimiento y, a continuación, restaurar la disponibilidad cuando el mantenimiento se haya completado.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Los administradores no pueden obtener el recuento de licencias mediante el cmdlet Get-CsClientAccessLicense

**Vulnerabilidad**

Los administradores no pueden obtener un uso preciso de licencias de cliente mediante el cmdlet **Get-CsClientAccessLicense** .

**Solución alternativa**

Para comprobar el tipo de licencia de servidor, puede ejecutar el cmdlet **Get-CsService** para recuperar los nombres de dominio completos (FDQNs) de todas las bases de datos. Si el FQDN del servidor front-end es el mismo que el FQDN de la base de datos back-end, la licencia es una licencia Standard Edition. De lo contrario, la licencia es una licencia de Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>El número de licencias de cliente no se ha notificado de forma precisa

**Vulnerabilidad**

Al determinar los recuentos de licencias de los clientes, es posible que se produzcan las siguientes condiciones:

1.  **Recuento de licencias inexacto para usuarios móviles**
    
    El recuento de licencias se basa en el número de direcciones IP únicas para los usuarios basados en dispositivos. El recuento de licencias se limitará de las siguientes maneras:
    
      - Las licencias se sobrescribirán si la dirección IP del usuario cambia durante las sesiones de Lync. Esto puede ocurrir cuando un usuario se conecta a Lync Server desde más de una ubicación con un cliente de escritorio.
    
      - Las licencias se recontarán si un usuario se conecta a un cliente móvil, ya que no se puede determinar la dirección IP para el dispositivo.

2.  **Las licencias se cuentan dos veces para llamadas de red telefónica conmutada (RTC) a clientes de Lync, llamadas de cliente de Lync a líneas RTC y llamadas de Lync a líneas RTC**
    
    En los siguientes escenarios, se contarán dos licencias adicionales en lugar de una porque tanto el número de teléfono como el usuario de Lync se tienen en cuenta para determinar el número de licencias que se usan. Para obtener datos de licencias precisos, quite manualmente las licencias generadas por un número de teléfono.
    
      - Una llamada telefónica RTC a Lync
    
      - Una llamada de Lync a una línea RTC
    
      - Una llamada RTC a Lync y, a continuación, Lync reenvía la llamada a una línea RTC. Se contará con una de las líneas RTC.

3.  **No se contará una licencia para un teléfono de Lync conectado**
    
    Cuando un usuario usa un teléfono certificado por Lync, si el teléfono inicia sesión y se mantiene conectado, lo cual conserva su estado de inicio de sesión, el teléfono no se contará como si estuviera usando una licencia si la consulta de licencias se produce después de que el teléfono haya iniciado sesión.

4.  **Licencias contadas para teléfonos RTC que se unen a conferencias**
    
    Cuando un usuario se une a una conferencia con un teléfono RTC, se contará con una licencia de forma inexacta para unirse a la Conferencia. Sin embargo, no se necesita ninguna licencia para unirse a una conferencia con un teléfono PSTN.

**Solución alternativa**

1.  **Recuento de licencias inexacto para usuarios móviles**
    
      - Puede identificar manualmente las direcciones IP que pertenecen al mismo dispositivo y, a continuación, quitar una de ellas en el recuento de licencias.
    
      - No hay ninguna solución alternativa para este problema con los dispositivos móviles que se conectan con el cliente de Lync.

2.  **Las licencias se cuentan dos veces para las llamadas RTC al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync a las líneas RTC**
    
    Tendrá que identificar manualmente el número de teléfono RTC y quitar el recuento de licencias generado para él.

3.  **No se contará una licencia para un teléfono de Lync que ha iniciado sesión**
    
    Puede configurar el teléfono de Lync para cerrar sesión y, a continuación, volver a iniciar sesión, a intervalos regulares, como cada 3 meses.

4.  **Licencias contadas para teléfonos RTC que se unen a conferencias**
    
    Puede identificar manualmente el número de teléfono RTC que se usa para unirse a la Conferencia y quitar la licencia generada por el número de teléfono.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>El panel de control de Lync Server deja de funcionar en un entorno de VMware después de actualizar a Silverlight 5

**Vulnerabilidad**

Si usa el panel de control de Lync Server en un entorno de VMware, es posible que el panel de control de Lync Server deje de funcionar después de actualizar Microsoft Silverlight a la versión 5.

**Solución alternativa**

Para solucionar este problema, realice una de las siguientes acciones:

  - Desinstale Silverlight 5 e instale Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).

  - Obtener acceso al panel de control de Lync Server desde un equipo que no es un equipo virtual de VMware.
    
    Para ello, puede iniciar el panel de control de Lync Server en el menú **Inicio** de Windows en el servidor, si las herramientas de administración de Lync Server están instaladas en el equipo.
    
    También puede obtener acceso al panel de control de Lync Server mediante un explorador Web. La dirección URL será similar a https://\<Front\_-\_end\>Pool FQDN/CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>La información de usuario del servicio de libreta de direcciones no se actualiza después de que se modifique el nombre completo del usuario en Active Directory

**Vulnerabilidad**

Si se cambia el nombre completo de un usuario (también conocido como DN) en servicios de dominio de Active Directory, los cambios adicionales no se actualizarán en el servicio de libreta de direcciones (ABS). Esto no afecta al inicio de sesión ni a la presencia del usuario, pero evitará la comunicación para el usuario si también cambia la dirección SIP, ya que las búsquedas devolverán una dirección SIP obsoleta.

**Solución alternativa**

Para solucionar este problema, no cambie el nombre completo de un usuario. Si revierte el nombre completo para el usuario al valor anterior, las actualizaciones se reflejarán en el servicio de libreta de direcciones.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Instalación

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>El uso de caracteres que no sean ASCII puede dar lugar a que no se inicie Lync Server

**Vulnerabilidad**

El programa de instalación fallará si el nombre de la carpeta de destino incluye caracteres que no son ASCII (incluidos Unicode, juego de caracteres de doble byte (DBCS), UTF-8 y UTF-16). Además, es posible que el programa de instalación se complete correctamente, pero el servidor no se iniciará si alguno de los caracteres que no son ASCII está contenido en alguno de los siguientes elementos:

  - Nombre del equipo

  - Nombre de dominio

  - Nombre de usuario

  - URI del SIP del usuario

  - Nombre de la cuenta de servicio

**Solución alternativa**

Use solo caracteres ASCII en el nombre de la carpeta de destino, el nombre del equipo, el nombre de dominio, el nombre de usuario, el URI SIP del usuario y los nombres de cuenta de servicio.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>El Hotfix para "el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS 7,5" debe estar instalado antes de instalar Lync Server 2013

**Vulnerabilidad**

El Hotfix de "el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), que se describe en el[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)artículo 264886 () de Microsoft Knowledge base, debe instalarse antes de instalar Lync Server 2013.

**Solución alternativa**

Descargue e instale el Hotfix desde el centro de descarga de [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft en.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 no se puede instalar en la versión de RTM del sistema operativo ITA de Windows Server 2012

**Vulnerabilidad**

Error en la instalación de Lync Server 2013 en Windows Server 2012 de ITA debido a errores en la instalación de Windows fabric.

Error en la instalación de Windows fabric porque las trazas de tejido se crean con el formato de hora HH: MM: SS. Sin embargo, en ITA Windows Server, el formato de hora es HH. MM.SS.

**Solución alternativa**

Para solucionar este problema, actualice el registro del sistema antes de instalar Lync Server 2013. La clave del registro que necesita actualizarse es: usuarios\_\\HKEY. \\STimeFormat\\predeterminado del panel\\de control. Cambie el valor de sTimeFormat a HH: mm: SS usando la interfaz de línea de comandos de Windows PowerShell de la siguiente manera:

1.  Inicie Windows PowerShell y ejecute los siguientes cmdlets:
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Para ver el valor actual, ejecute el siguiente cmdlet:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Anote el valor actual de sTimeFormat para que se pueda restaurar una vez completada la instalación.

3.  Para establecer en nuevo valor, ejecute el siguiente cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Después de instalar Lync Server 2013 correctamente, restaure el valor original de la sTimeFormat ejecutando el siguiente cmdlet:
    
        - Set-ItemProperty $a-Name sTimeFormat "<valor que se anota en el paso 3. encima de> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Movilidad

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemas para clientes móviles durante el proceso de conmutación por error del servidor

**Vulnerabilidad**

Cuando se produce un error en Lync Server y comienza el proceso de conmutación por error, los siguientes problemas pueden afectar a los usuarios de clientes móviles:

  - No hay ninguna llamada o señal de Lync entrante durante un máximo de 10 minutos después de que se inicie la conmutación por error.

  - No se aceptan solicitudes entrantes de chat

  - No se pueden unir reuniones si el servidor con error es el servidor principal para el usuario

**Solución alternativa**

No hay ninguna solución para este problema. La funcionalidad normal se restaurará una vez que se complete el proceso de conmutación por error.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Si un usuario móvil rechaza una llamada entrante desde otro extremo de Lync, la llamada se muestra como una conversión perdida en clientes móviles de Lync.

**Vulnerabilidad**

Si un usuario móvil rechaza una llamada entrante y la llamada se originó desde otro extremo de Lync, la llamada se muestra como una conversación perdida en el cliente móvil de Lync, en lugar de una llamada en la lista de llamadas de dispositivo.

**Solución alternativa**

No hay ninguna solución para este problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Es posible que el cliente móvil no muestre el nombre para mostrar de un contacto federado al buscar contactos

**Vulnerabilidad**

Es posible que el nombre para mostrar de los contactos federados no se muestre en algunos escenarios, como cuando se busca un contacto federado en la lista de contactos. Esto puede ocurrir cuando no hay una suscripción de presencia activa para el contacto desde el cliente móvil de Lync.

**Solución alternativa**

No hay ninguna solución para este problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>En el cliente móvil, falta la información de la invitación y la marca de hora de una conversación perdida que es una invitación a una conferencia

**Vulnerabilidad**

En el cliente móvil, cuando una conversación perdida es una invitación a una conferencia, la información de la invitación y la marca de hora no se encuentra en el mensaje de conversación perdido.

**Solución alternativa**

No hay ninguna solución para este problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Los usuarios de clientes móviles que hacen llamadas mediante VoIP no pueden abandonar el correo de voz para los usuarios cuyo correo de voz esté configurado en Exchange 2010 o versiones anteriores.

**Vulnerabilidad**

Si un usuario de un cliente móvil usa VoIP para realizar llamadas, el usuario no podrá dejar mensajes de correo de voz para los usuarios configurados para usar el correo de voz en Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.

**Solución alternativa**

Para solucionar este problema, use Exchange 2010 con SP1 o una versión posterior de Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Al usar Block con URL para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto

**Vulnerabilidad**

Cuando se usa **Block with URL** para la configuración de la versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto cuando la versión del cliente no es compatible.

**Solución alternativa**

Para evitar este problema, configure la versión del cliente para que use **Block** en lugar de **Block with URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conferencias

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>El software antivirus que se ejecuta en los servidores front-end de Lync Server 2013 puede provocar reciclado del dominio de la aplicación, que interrumpe temporalmente el servicio para Lync Web App 2013, Lync Mobile 2010 y clientes de Lync Mobile 2013

**Vulnerabilidad**

El software antivirus puede desencadenar el reinicio del dominio de la aplicación, lo que puede dar como resultado aplicaciones de cliente de Lync Mobility Service 2013 y comunicaciones unificadas (UC) web API (Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013) para perder su estado.

**Solución alternativa**

Para evitar este problema, excluya las carpetas que contienen los componentes Web y .NET Framework de la detección de virus. Para obtener más información, consulte el artículo 312592 de Microsoft Knowledge base, "error PRB: el reinicio de la aplicación aleatoria con ' la aplicación se está reiniciando" en ASP.NET [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).

Se deben excluir las siguientes carpetas:

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\de Ucwa int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\de Ucwa ext

  - % WINDIR%\\Microsoft.net\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Los controles ActiveX o la compatibilidad de XMLHTTP nativa deben estar habilitados en Windows Internet Explorer para unirse correctamente a las conferencias

**Vulnerabilidad**

Si un usuario ha deshabilitado los controles ActiveX y la compatibilidad con XMLHTTP nativa en la configuración del explorador de Internet de Windows Internet Explorer, el usuario no podrá unirse a una reunión si Internet Explorer está seleccionado como el explorador predeterminado.

**Solución alternativa**

Habilite los controles ActiveX o la "compatibilidad con XMLHTTP nativo" en Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>El servicio de conferencias web de Lync Server no puede recuperarse desde el modo crítico

**Vulnerabilidad**

Si se activa el modo crítico para el archivado, en caso de que se produzcan errores en el sistema, se iniciará el modo crítico y las conferencias dejarán de funcionar para los participantes. Una vez que el administrador soluciona los errores del sistema (como corregir un problema de la base de datos), el servicio Conferencia de datos no se recupera automáticamente y el administrador debe reiniciar manualmente el servicio de conferencia para que se reanude la Conferencia.

**Solución alternativa**

Un administrador debe reiniciar manualmente el servicio de conferencia después de que se haya corregido el error del sistema.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>El servicio de conferencias por Internet omite el proxy HTTP para servidores externos de Office Web App

**Vulnerabilidad**

Si ha implementado un servidor de Office Web Apps externo al servicio de conferencias web (es decir, un servidor que no está en la red corporativa interna) en Internet, la red perimetral y el servicio de conferencias web requiere un proxy HTTP para conectarse a este, el Se producirá un error en la detección de Office Web Apps Server. El servicio de conferencias por Internet pasa por alto la configuración de proxy HTTP, según se define en el generador de topologías para la configuración de Office Web Apps Server. Como resultado, el cliente de Lync no podrá compartir Microsoft PowerPoint 2010 con otros participantes de la Conferencia. Si está instalando Lync Server local y también configura Office Web Apps Server local en la red interna, no se requiere una configuración de proxy.

**Solución alternativa**

La única solución alternativa es no tener una configuración de implementación que requiera el uso de proxy HTTP para comunicarse con un servidor externo de Office Web Apps.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>No se admite Agregar vídeo a una conferencia de proveedor de servicios de audioconferencia.

**Vulnerabilidad**

No se puede Agregar un vídeo si el usuario se une a una conferencia de proveedor de servicios de audioconferencia para el audio.

**Solución alternativa**

No hay ninguna solución para este problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologías con IPv6 habilitada fuerce la actualización automática del complemento Silverlight Web App Silverlight para garantizar que la funcionalidad de pantalla compartida pueda funcionar desde Lync Web App

**Vulnerabilidad**

Cuando una topología está configurada con IPv6 habilitado, los usuarios no pueden compartir su pantalla desde el cliente de Lync Web App si ya está instalada una versión anterior del complemento de uso compartido de pantalla.

**Solución alternativa**

Para forzar una actualización a la versión más reciente del complemento de uso compartido de la pantalla al unirse a una reunión a través de Lync Web App, modifique el valor de **MinSupportedBuildVersion** de "4.0.7457.0" a "4.0.7577.380" en los dos archivos siguientes:

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\póngase\\en\\contacto con\\los\\complementos de cliente int ReachAppShPluginProperties. XML

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\\\\\plug and ext Plug\\and ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Telefonía IP empresarial

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>En algunos casos, es posible que un cliente de Lync que se ejecuta en un equipo configurado para usar IPv4 e IPv6 Dual Stack no admita capacidades basadas en la subred IP del equipo, como E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en la ubicación.

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



</div>

**Vulnerabilidad**

Cuando un cliente de Lync se ejecuta en un equipo que está habilitado para IPv4 e IPv6 Dual Stack y en función de la resolución DNS del servidor proxy, el cliente puede usar la dirección IPv6 del equipo para iniciar sesión. Después de hacerlo, el cliente de Lync solo admitirá las capacidades admitidas para IPv6, que excluye E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en la ubicación.

**Solución alternativa**

Para solucionar este problema, deshabilite la compatibilidad de IPv6 en el equipo cliente.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Si la telefonía IP empresarial no está configurada para un usuario, el usuario tendrá que usar el formato E164 para llamar desde una conferencia.

**Vulnerabilidad**

Si la telefonía IP empresarial no está configurada para un usuario, ese usuario tendrá que usar el formato E164 para llamar correctamente desde una conferencia. Si no se usa el formato E164, el usuario no podrá llamar desde la Conferencia.

**Solución alternativa**

Para evitar este problema, los usuarios que no tengan habilitada la telefonía IP empresarial deben llamar desde una conferencia usando números en formato E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Presence

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechazará cuando deba

**Vulnerabilidad**

Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechazará cuando deba.

**Solución alternativa**

Para evitar este problema, puede desactivar el almacén de contactos unificado para el usuario. Para ello, ejecute los siguientes cmdlets:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Por ejemplo:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Los usuarios de Office Communications Server 2007 R2 alojados localmente no pueden ver el estado de presencia de los usuarios de Skype empresarial online en implementaciones híbridas: híbrida

**Vulnerabilidad**

El problema puede ocurrir en una implementación híbrida cuando usa un director de 2013 de Lync Server.

El estado de presencia de los usuarios alojados en Skype empresarial online se muestra como una presencia desconocida para los usuarios locales. Además, los usuarios alojados en Skype empresarial online no pueden ver el estado de presencia de los usuarios locales de Office Communications Server R2.

**Solución alternativa**

Para evitar parcialmente este problema, cambie el servidor principal (msRTCSIP-presencehomeserver) de los usuarios de Skype empresarial online para que apunten a un grupo local de Lync Server 2013 en lugar del Director de Lync Server 2013. Puede modificar esta configuración en el servidor front-end local.

Esta solución alternativa mostrará correctamente el estado de presencia de los usuarios alojados en Office Communications Server 2007 R2 a usuarios de Skype empresarial online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas y recogida de llamada grupal

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Una persona que llama puede oír un segundo de música en espera durante el establecimiento de una llamada con la parte receptora

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



</div>

**Vulnerabilidad**

Cuando se recupera una llamada a través de la recogida de llamadas grupales, es posible que la persona que llama escuche un segundo de la música en espera durante el establecimiento de la llamada con el ampliador de la fiesta.

**Solución alternativa**

No hay ninguna solución para este problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agente de grupo de respuesta puede iniciar sesión y cerrar sesión en una consola del agente de 2010 de Lync Server para Lync Server 2010 solo grupos de agentes formales

**Vulnerabilidad**

Un agente de grupo de respuesta de Lync Server 2013 puede iniciar sesión y cerrar sesión a través de una consola del agente de Lync Server 2010 para Lync Server 2010 solo grupos de agente formal. En la consola del agente de Lync Server 2010, los usuarios solo pueden ver el grupo de respuesta de Lync Server 2010 al que pertenecen. No pueden ver ninguno de los grupos de respuesta de Lync Server 2013 a los que pertenecen.

**Solución alternativa**

Si el agente de grupo de respuesta es un usuario de Lync Server 2013 y parte de un grupo de agentes formales de Lync Server 2013, el usuario debe tener acceso a la consola del agente de Lync Server 2013 directamente a través de un vínculo Web en un explorador para iniciar y cerrar sesión en los grupos de agentes de Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agente de grupo de respuesta 2010 de Lync Server no puede realizar llamadas en nombre de un grupo de respuesta de Lync Server 2013

**Vulnerabilidad**

Un usuario de Lync Server 2010 que es un agente de un grupo de respuesta de Lync Server 2013 no puede realizar una llamada en nombre del grupo de respuesta. El grupo de respuesta de Lync Server 2013 no estará disponible en el cliente de Lync para realizar una llamada.

**Solución alternativa**

Para solucionar este problema, debe mover el usuario de Lync Server 2010 a Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Quitar un grupo de respuesta de Lync Server 2010 después de migrarlo a Lync Server 2013 evitará que el grupo de respuesta acepte llamadas entrantes.

**Vulnerabilidad**

Si un grupo de respuesta migrado de Lync Server 2010 a Lync Server 2013 se quita de Lync Server 2010 a través del panel de control de Lync Server o del shell de administración de Lync Server, el grupo de respuesta de Lync Server 2013 dejará de recibir las llamadas entrantes.

**Solución alternativa**

Para solucionar este problema, no quite los grupos de respuesta de Lync Server 2010 que se hayan migrado de Lync Server 2010 a Lync Server 2013.

Si el grupo de respuesta ya se ha quitado, debe volver a implementarlo en Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Cuando un nuevo flujo de trabajo administrado se establece como inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo.

**Vulnerabilidad**

Cuando se establece un nuevo flujo de trabajo administrado como inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo. Este problema se produce cuando el flujo de trabajo se establece como inactivo cuando se crea, pero no afecta a un flujo de trabajo que se modifica para establecerlo en inactivo una vez que se ha implementado.

**Solución alternativa**

Al crear e implementar un flujo de trabajo, establezca el flujo de trabajo como activo y, a continuación, impleméntelo. Una vez que el flujo de trabajo se ha implementado correctamente, el flujo de trabajo se puede editar y establecer en inactivo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Al quitar un grupo de respuesta del grupo de propietarios evitará que el grupo de respuesta del grupo de copias de seguridad acepte llamadas entrantes durante la conmutación por error si el grupo de respuesta se ha importado al grupo de copia de seguridad.

**Vulnerabilidad**

Si un grupo de respuesta que pertenece al grupo principal se ha importado al grupo de copia de seguridad sin sobrescribir el propietario y el grupo de respuesta se quita del grupo de propietarios, el grupo de respuesta del grupo de copia de seguridad no aceptará ninguna llamada entrante durante la conmutación por error.

**Solución alternativa**

Tendrá que volver a implementar el grupo de respuesta en el grupo primario. Después, tendrá que exportar la configuración del grupo de respuesta del grupo principal e importarla de nuevo al grupo de copias de seguridad.

También puede volver a crear el grupo de respuesta en el grupo de copia de seguridad. En este caso, el grupo de copia de seguridad será el grupo de propietarios del grupo de respuesta.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>No se puede recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas si la solicitud de recuperación se realiza en nombre de un grupo de respuesta

**Vulnerabilidad**

Cuando se cumplan las condiciones siguientes, se producirá un error en una solicitud de recuperación para una llamada en aparcada:

  - Un agente forma parte de un grupo de respuesta anónimo

  - El agente intenta recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas a través del grupo de respuesta anónima

  - El agente intenta recuperar la llamada marcando el número de órbita a través de la opción llamar en nombre o a través de la misma opción en el cliente del operador de Lync.

**Solución alternativa**

No hay ninguna solución para este problema. La llamada estacionada debe recuperarse sin hacerlo en nombre de un grupo de respuesta.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Panel de control de Lync Server, Generador de topologías y Herramienta de planeación

<div>

## <a name="planning-tool-limitations"></a>Limitaciones de la herramienta de planeación

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



</div>

**Vulnerabilidad**

La herramienta de planeación tiene las siguientes limitaciones al planear la implementación:

  - Hay un máximo de 10 sitios centrales admitidos

  - Cada sitio central puede tener un máximo de 14 sitios de sucursales

  - Cada sitio central puede tener un máximo de 240.000 usuarios

Además, la herramienta de planeación no incluye los valores de los siguientes en el cálculo de la topología recomendada:

  - El número de usuarios alojados en línea

  - El porcentaje de usuarios que están habilitados para la Federación de XMPP

  - Porcentaje de usuarios que usan Lync Web App

**Solución alternativa**

No hay ninguna solución para estos problemas. Para obtener más información sobre la herramienta de planeación, consulte [diseño de la topología de Lync Server 2013 mediante la herramienta de planeación](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Es posible que la herramienta de planeación no use las direcciones IP definidas previamente para la red perimetral al actualizar las opciones

**Vulnerabilidad**

Después de completar el diseño con la herramienta de planeación, si realiza cambios en las opciones de red perimetral, se pueden agregar direcciones IP adicionales al diseño en lugar de actualizar las direcciones IP existentes. Esto puede ocurrir si está viendo los detalles del diagrama de red perimetral, seleccione **haga clic aquí para actualizar las opciones**y, a continuación, en el cuadro de diálogo Opciones de configuración, seleccione red perimetral, seleccione **deseo usar los mismos FQDN y direcciones IP, pero distintos puertos para los servicios perimetrales de mi servidor perimetral**. Aplicar los cambios puede dar lugar a que se agreguen nuevas direcciones IP y servidores perimetrales al diseño.

**Solución alternativa**

En este momento no hay ninguna solución para este problema.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>En el panel de control de Lync Server, "mover todos los usuarios al grupo" puede no funcionar según lo esperado

**Vulnerabilidad**

Cuando se usa el panel de control de Lync Server para mover todos los usuarios de un grupo a otro en un entorno complejo de Active Directory, como uno con varios controladores de dominio y dominios primarios y secundarios, se puede devolver un mensaje de error que indica que "el usuario especificado no es un usuario heredado, use en su lugar el cmdlet Move-CsUser". Este es el resultado de tiempos de replicación más largos en entornos complejos de Active Directory.

**Solución alternativa**

Para solucionar este problema, realice una de las siguientes acciones:

  - Use filtros en el panel de control de Lync Server para buscar usuarios heredados, selecciónelos y, a continuación, use el **comando mover usuarios seleccionados a la agrupación** en lugar de **mover todos los usuarios al grupo**.

  - Use el shell de administración de Lync Server para mover usuarios heredados en lotes mediante el uso de cmdlets de Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>El panel de control de Lync Server deja de funcionar en un entorno de VMware después de que el complemento de explorador Microsoft Silverlight se actualice a la versión 5

**Vulnerabilidad**

Si usa el panel de control de Lync Server en un entorno de VMware, es posible que el panel de control de Lync Server deje de funcionar después de actualizar Silverlight a la versión 5.

**Solución alternativa**

Para solucionar este problema, realice una de las siguientes acciones:

  - Desinstale Silverlight 5 y, a continuación, instale Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)4 desde.

  - Abra el panel de control de Lync Server desde un equipo que no sea un equipo virtual de VMware.
    
    Para abrir el panel de control de Lync Server desde un equipo remoto, instale las herramientas de administración de Lync Server en el equipo y, a continuación, inicie el panel de control de Lync Server en el menú **Inicio** de Windows.
    
    También puede abrir el panel de control de Lync Server escribiendo la dirección URL en un explorador Web. La dirección URL será similar a https://\<Front\_-\_end\>Pool FQDN/CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un administrador no puede ejecutar el cmdlet Uninstall-csMirrorDB después de quitar la base de datos de reflejo en el generador de topologías

**Vulnerabilidad**

Cuando un administrador deshabilita una base de datos de reflejo en el generador de topología y, a continuación, elimina la base de datos de reflejo en el generador de topología, se muestra un mensaje en la lista de tareas pendientes para que el administrador ejecute el cmdlet **Uninstall-csMirrorDatabase** para quitar el reflejo de SQL Server. Cuando el administrador intenta ejecutar el cmdlet, se produce un error.

**Solución alternativa**

Para quitar la creación de reflejos de SQL de un grupo en el generador de topología, primero debe usar un cmdlet para quitar el reflejo en SQL Server. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por ejemplo, para quitar el reflejo y colocar las bases de datos de las bases de datos de usuario, escriba lo siguiente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

El parámetro *DropExistingDatabasesOnMirror* hace que las bases de datos afectadas se eliminen del reflejo. Luego, para quitar el reflejo de la topología, haga lo siguiente:

1.  En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.

2.  Desactive habilitar el reflejo de la **tienda SQL** y haga clic en **Aceptar**.

3.  Publique la topología.

<div class="">


> [!IMPORTANT]  
> Siempre que realice un cambio en una relación de reflejo de la base de datos back-end, debe reiniciar todos los servidores front-end del grupo.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Los errores de validación se devuelven en el generador de topología cuando un administrador intenta quitar una implementación con un grupo de servidores front-end que tiene un almacén testigo asociado

**Vulnerabilidad**

Si un administrador intenta usar el comando **quitar implementación** del generador de topología para quitar una implementación que incluye un grupo de servidores front-end con un almacén testigo asociado, se muestra un error de validación en el generador de topologías y la acción no continuará.

**Solución alternativa**

Para solucionar este problema, realice una de las siguientes acciones:

  - Quite el almacén testigo antes de intentar quitar la implementación.

  - Agregue una tienda de testigos para el grupo de servidores front-end y, a continuación, quítela.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>La información de implementación del servidor de chat persistente es incoherente entre la herramienta de planificación y el generador de topología

**Vulnerabilidad**

Cuando el 2013 de Lync Server, la herramienta de planeación genera el diagrama de topología del sitio para una implementación de servidor de chat persistente con la recuperación de desastres habilitada, el diagrama de topología del sitio incluye varios sitios (físicos), con servidores de chat persistentes asignados uniformemente en cada uno de ellos. Ubicación. En el generador de topología, todos los servidores de chat persistentes se representan como pertenecientes a un único sitio (lógico) y se enumeran en el mismo nodo del grupo de servidores de chat persistente.

**Solución alternativa**

Por el momento, no tenemos ninguna solución para este problema. El usuario debe analizar el resultado de la herramienta de planeación de la implementación del servidor de chat persistente y modificar el plan para satisfacer sus necesidades específicas.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Local

<div>

## <a name="monitoring"></a>Supervisión

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>El asistente implementar informes de supervisión muestra caracteres incorrectos en determinadas circunstancias al usar la versión de Lync Server de Asia oriental

**Vulnerabilidad**

Al usar una versión de Lync Server 2013 para Asia Oriental (por ejemplo, Chino (simplificado), Chino (tradicional), Japonés o coreano, en un sistema operativo que tiene la configuración regional del sistema no establecida en un idioma de Asia oriental, el Asistente para implementar informes de supervisión le mostrar signos de interrogación u otros caracteres en lugar de mensajes localizados.

**Solución alternativa**

Para corregir este problema, establezca la configuración regional del sistema operativo y de Lync Server 2013 en el mismo idioma, lo que mostrará todos los mensajes correctamente.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Panel de control de Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>En algunos casos, el primer elemento de la barra de navegación superior de una página del panel de control de Lync Server desaparece cuando se hace clic en el último elemento de la barra de navegación superior

**Vulnerabilidad**

Hay tres casos conocidos en los que, al hacer clic en el último elemento de la barra de navegación superior de una página del panel de control de Lync Server, el primer elemento de la barra de navegación superior desaparece:

  - En el francés de la versión, en la página "Féderation et Accès externo", el elemento "Stratégie d'accès extern" desaparecerá cuando se haga clic en "partenaires Fédérés XMPP".

  - En la versión alemana, en la página "clientes", el elemento "Clientversionskonfiguration" desaparece cuando se hace clic en "Pushbenachrichtigungskonfiguration".

  - En la versión rusa, en la página "Конфигурация сети", el elemento "Глобально" desaparece cuando se hace clic en "Маршрут региона".

**Solución alternativa**

Para solucionar este problema, actualice la página del panel de control de Lync Server en el explorador. La página se cargará en el explorador con todos los elementos de la barra de navegación superior mostrada.

</div>

</div>

<div>

## <a name="address-book"></a>Libreta de direcciones

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>La indización de la libreta de direcciones no funciona de la forma esperada en algunos idiomas

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



</div>

Si las propiedades de un usuario contienen un campo indizado y ese campo solo contiene caracteres que no se pueden indizar, el usuario no aparecerá en las búsquedas realizadas en la libreta de direcciones.

Los siguientes caracteres y configuraciones regionales no se pueden indizar:

  - Caracteres cirílico, griego y armenio en mayúsculas

  - Caracteres con acento mayúscula

  - Tailandés

  - Lao

  - Myanmar

  - Devanagari

  - Dígito

  - Tibetano

  - Bengalí

  - Gujarati

  - Telugu

  - Todas las demás secuencias de comandos indios

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, programador web y componentes Web

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>La reserva de idioma para algunos idiomas en el programador web de Lync, el acceso telefónico, el iniciador de la Unión, la administración de salones de chat persistente y OCTab podría no funcionar de la manera esperada

**Vulnerabilidad**

Al seleccionar una configuración regional neutra en un explorador Web (en Internet Explorer), por ejemplo, el nombre del idioma sin especificación adicional, como \["\]noruego no") en lugar de una configuración regional que especifique el idioma, la secuencia de comandos y la configuración regional (como " \[noruego, BOKMÅL\](Noruega) NB-no") podría provocar un comportamiento de visualización inesperado para algunos idiomas de Lync web Scheduler, acceso telefónico, iniciador de chat, administración de salones de chat Por ejemplo, es posible que los usuarios vean la página en inglés cuando se selecciona uno de los siguientes idiomas:

  - Noruego

  - Portugués

  - Serbio

**Solución alternativa**

Si desea seleccionar un idioma con una configuración regional neutra, asegúrese siempre de agregar el idioma con una configuración regional específica (con el código de la secuencia de comandos o el país) como idioma adicional en la lista de preferencias de idioma del explorador.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Hay compatibilidad limitada con las configuraciones regionales azerí y uzbeko cuando se usa el programador web de Lync, el acceso telefónico, el iniciador de unirse, la administración de salones de chat persistente y OCTab en algunos exploradores Web.

<div class="">


> [!NOTE]  
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



</div>

**Vulnerabilidad**

Cuando usa Internet Explorer 8 o Internet Explorer 9, y establece el idioma del explorador en Azerí (Latino) o uzbeko (Latino), las páginas de acceso telefónico local y de iniciador de la Unión se mostrarán en inglés o en el idioma preferido establecido en el explorador.

Al usar los exploradores Firefox o Chrome, y establecer el idioma del explorador en Azerí (Latino) o uzbeko (Latino), Lync Web App, Lync web Scheduler y RGS OCTab se mostrará en inglés o en el idioma preferido establecido para el explorador.

La configuración regional uzbeko (Latino) no es compatible con el explorador Safari.

**Solución alternativa**

No hay solución para estos problemas.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>Falta la flecha desplegable de la lista "unirse a la reunión desde" en la versión rumano de Lync Web App

**Vulnerabilidad**

Cuando un usuario que usa la versión rumano de Lync Web App realiza los siguientes pasos, la flecha desplegable no se muestra para unirse a la **reunión** en la lista desplegable:

1.  Seleccione **recordar mis en este equipo** en la pestaña **General** .

2.  Seleccione la pestaña **teléfono** .

3.  Haga clic en la lista desplegable para unirse a la **reunión desde**.
    
    Los usuarios no verán una flecha que indica que hay más opciones que la predeterminada de **Lync Web App**, entre las que se incluyen: **no unirse al audio** (en el rumano, "nu se asociaža la aplicación audio") y al **nuevo número**"(en rumano," Număr Nou ").

**Solución alternativa**

Aunque no se muestre la flecha de esta lista desplegable, los usuarios pueden seguir seleccionando la configuración adicional en la lista haciendo clic en el valor predeterminado.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Al usar la versión turca de Lync web Scheduler, no se puede guardar una reunión al usar la opción "las personas que elijo" en "quién es un moderador".

**Vulnerabilidad**

Al crear o editar una reunión en la versión turca del programador web de Lync, no se admite la opción "las personas que elijo" en "¿quién es un moderador". Cuando esta opción está seleccionada, la reunión no se puede guardar. En su lugar, aparece un mensaje de error que indica que una o más personas no pueden hacerse moderadores.

**Solución alternativa**

Para evitar este problema, los usuarios pueden usar la opción predeterminada "personas de mi compañía" o cualquier otra opción, como "solo Organizer" o "todos las personas que no pertenecen a mi compañía". El organizador puede disminuir o promover a los usuarios a sus roles correctos después de que se hayan unido a la reunión.

Como alternativa, los usuarios que entienden otro idioma pueden cambiar la selección de idioma en el explorador a uno de los otros idiomas admitidos por 43 e intentar usar la opción "las personas que elijas".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Tratados

Este documento es una versión preliminar de un producto de software que puede cambiar sustancialmente antes del lanzamiento comercial final, y es la información confidencial y de propiedad de Microsoft Corporation. Se revelará conforme a un acuerdo de no divulgación entre el destinatario y Microsoft. Este documento se proporciona solo a título informativo y Microsoft no otorga garantías expresas ni implícitas en este documento. La información de este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a cambios sin previo aviso. El riesgo completo del uso o los resultados del uso de este documento se mantiene con el usuario. A menos que se indique lo contrario, las empresas, las organizaciones, los productos, los nombres de dominio, las direcciones de correo electrónico, los logotipos, las personas, los lugares y los acontecimientos descritos en los ejemplos son ficticios. No se pretende indicar ni debe deducirse ninguna asociación con ninguna compañía, organización, producto, nombre de dominio, dirección de correo electrónico, logotipo, persona, lugar o acontecimiento reales. El cumplimiento de todas las leyes de propiedad intelectual vigentes es responsabilidad del usuario. Sin limitación de los derechos de propiedad intelectual, ninguna parte de este documento puede ser reproducida, almacenada o introducida en un sistema de recuperación o transmitida de ninguna forma ni por ningún medio (electrónico, mecánico, Fotocopiado, grabación o de otra manera), ni con ningún propósito, sin los permisos expreso y por escrito de Microsoft Corporation.

Microsoft puede tener patentes, solicitudes de patentes, marcas comerciales, derechos de propiedad intelectual u otros derechos de propiedad intelectual sobre los contenidos de este documento. A excepción de lo estipulado expresamente en un contrato de licencia por escrito de Microsoft, el suministro de este documento no le otorga ninguna licencia para estas patentes, marcas comerciales, derechos de propiedad intelectual u otros derechos de propiedad intelectual.

© 2012 Microsoft Corporation. Todos los derechos reservados.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook y SQL Server son marcas comerciales o marcas comerciales registradas de Microsoft Corporation en los Estados Unidos y en otros países o regiones.

El resto de marcas comerciales pertenecen a sus respectivos dueños.

</div>

</div>

<span> </span>

</div>

</div>

</div>

