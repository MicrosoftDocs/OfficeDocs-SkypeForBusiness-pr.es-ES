---
title: 'Lync Server 2013: Notas de la versión'
TOCTitle: Notas de la versión
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48276236
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Notas de la versión de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Estas son las Notas de la versión de Lync Server 2013. Consulte este archivo para obtener información sobre los problemas conocidos de Lync Server 2013.

## Acerca de este documento

Este documento contiene información importante que debe conocer antes de implementar y usar Lync Server 2013. Para más información sobre Lync Server 2013, vea la documentación de [Microsoft Lync Server 2013](microsoft-lync-server-2013.md).

Este documento contiene las siguientes secciones:
 
   Cliente de Lync 2013  
  
   Lync Server  
  
   Instalación  
  
   Movilidad  

   Conferencia  

   Telefonía IP empresarial  

   Presencia  

   Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas  

   Panel de control de Lync Server, Generador de topologías y Herramienta de planeación  
  
   Localización  
 
   Derechos de autor  

## Cliente de Lync 2013

## La transferencia de un archivo en un mensaje instantáneo falla si el archivo está abierto en otra aplicación (1920369)

**Problema:**

Si intenta transferir un archivo (como un documento de Word) incluyéndolo en un mensaje instantáneo para otro usuario de Lync, la transferencia aparece como realizada correctamente, aunque es posible que el archivo no se haya transferido. El cliente de Lync muestra el icono del tipo de archivo, pero el destinatario no puede abrirlo. No se muestra ningún mensaje de error para informar del error en la transferencia.

**Solución alternativa:**

Para evitar este problema, cierre el archivo o la aplicación que lo tiene abierto antes de intentar la transferencia en un mensaje instantáneo.

## Lync Server

## Si se produce un error en la replicación de datos del servicio de almacenamiento de Lync Server, los administradores deberán comprobar los contadores de rendimiento para ver si existen elementos obsoletos en la cola de este servicio (3225121)

**Problema:**

El servicio de almacenamiento de Lync Server usa Windows Fabric para la replicación. Si se eliminan datos en un Servidor front-end principal, pero se genera un error con la eliminación en un Servidor front-end secundario (por ejemplo, si se produce un cierre o error inesperado en el Servidor front-end), es posible que los datos se dejen de lado y queden "huérfanos". Los datos huérfanos pueden provocar la degradación del rendimiento y la pérdida de espacio en la unidad.

**Solución alternativa:**

Para solucionar este problema, si se generan los eventos LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) y LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) en el registro de eventos, los administradores deben comprobar en el contador de rendimiento del Servidor front-end la opción **LS:LYSS - Storage Service API** con el nombre **LYSS - Current number of Storage Service stale queue items**. Si este contador de rendimiento tiene un valor alto (por ejemplo, mayor que 50.000), el administrador debe ejecutar la herramienta CleanuUpStorageServiceData.exe del kit de recursos de Lync Server 2013, que eliminará todos los datos huérfanos del grupo de servidores. Para más información sobre la herramienta, vea la documentación del kit de recursos de Lync Server 2013.

## Cada vez que se cambia la configuración de la dirección IP de un servidor o grupo de servidores, se deben reiniciar los servicios de Lync Server (3212447)

**Problema:**

Cuando se cambia la configuración de la dirección IP de una implementación de Lync Server 2013, por ejemplo, cuando se cambia de IPv4 a pila doble o de pila doble a IPv6, no todos los componentes del servidor detectan el cambio de configuración hasta que se reinician los servicios.

**Solución alternativa:**

Para solucionar este problema, reinicie los servicios de Lync Server después de cambiar la configuración de la dirección IP de la implementación. Para ello, ejecute los siguientes cmdlets en el Shell de administración de Lync Server:

  ```
  Stop-CsWindowsService -graceful
  ```
  ```
  Start-CsWindowsService
  ```
## El cmdlet de transacciones sintéticas de conferencia de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013 (3212342)

**Problema:**

El cmdlet de transacciones sintéticas de conferencia de acceso telefónico local **Test-CsDialInConferencing** ya no está disponible en el módulo de administración de Lync Server 2013.

**Solución alternativa:**

El cmdlet de transacciones sintéticas de conferencia de acceso telefónico local **Test-CsDialInConferencing** solo se puede usar en una empresa de forma interna.

Los administradores pueden seguir usando el cmdlet en el Shell de administración de Lync Server para solucionar problemas. Si es necesario, una empresa también puede desarrollar un módulo de administración privado para ejecutar el cmdlet de forma interna.

## El servicio de registro centralizado se detiene si el tráfico de red se interrumpe cuando se copian archivos de registro a un recurso compartido de red (3212464)

**Problema:**

Cuando el servicio de registro centralizado se configura para usar una ruta de red (el valor del parámetro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** es una ruta UNC válida), los archivos de registro almacenados en caché se copian al recurso compartido de red. Si se produce una interrupción en el tráfico de red mientras se copian los archivos, se generará una excepción que provocará que el servicio de registro centralizado se detenga.

El servicio está configurado para reiniciarse automáticamente hasta tres veces y, por lo tanto, se recuperará de las primeras tres excepciones.

**Solución alternativa:**

No existe ninguna solución para este problema. Para identificar el problema, supervise en el registro de eventos el identificador de evento 7031 del Administrador de control de servicios que se registra cuando el agente del servicio de registro centralizado de Lync Server ha finalizado de forma inesperada. Si esto sucede más de tres veces, reinicie el servicio manualmente con el cmdlet **Start-CsWindowService**.

## Los elementos de la cola del servicio de almacenamiento se deben importar manualmente (3211368)

**Problema:**

Lync Server 2013 almacena datos sobre conferencias y mensajería instantánea, como mensajes archivados y un registro detallado de llamadas (CDR), en una base de datos en cada Servidor front-end. Los datos se almacenan en la base de datos mientras se procesan, antes de que se entreguen al destino correspondiente. Para mejorar el rendimiento, Lync Server 2013 exporta periódicamente de la base de datos local los elementos de la cola que no se hayan procesado en un período de tiempo prolongado, y los guarda en el almacén de archivos. Si el almacén de archivos no está disponible, los elementos se almacenan en cada Servidor front-end. Se realiza la misma operación para evitar la pérdida de datos durante la conmutación por error del grupo de servidores.

Durante la operación de exportación, el servicio de almacenamiento de Lync Server registra cada fase en el registro de eventos con los identificadores de evento 32075 (operación de vaciado completo iniciada), 32076 (vaciado completo finalizado), 32082 (vaciado de nivel de mantenimiento iniciado), 32083 (vaciado de nivel de mantenimiento finalizado) y 32089 (vaciado provocado por base de datos llena). Estos datos no se volverán a importar automáticamente al sistema para que se procesen y se entreguen a su destino final ( SQL Server o Exchange Server).

**Solución alternativa:**

Para importar los datos al sistema, los administradores deberán usar la herramienta ImportStorageServiceData del kit de recursos de Lync Server, que agregará los datos nuevamente al sistema para que se procesen y se envíen a su destino final.

## Se producirá un error en las búsquedas de la consulta web de la libreta de direcciones si el valor predeterminado de UseNormalizationRules se cambia a False (3175514)

**Problema:**

Si el valor predeterminado de UseNormalizationRules se cambia a False, se producirá un error en las búsquedas de la consulta web de la libreta de direcciones. Tras modificar el valor predeterminado, los usuarios del cliente de Lync no podrán usar la consulta web de la libreta de direcciones de Lync para buscar usuarios.

**Solución alternativa:**

Si el valor predeterminado de UseNormalizationRules se establece en False para que los usuarios puedan usar números de teléfono como se define en los Servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, solucione este problema de la siguiente manera:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Siga uno de estos pasos:
    
      - Si su implementación incluye solo servidores Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de UseNormalizationRules e IgnoreGenericRules a True:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores Lync Server 2013 de la topología:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere hasta que la replicación de CMS se complete en todos los grupos de servidores.

4.  Modifique el archivo de reglas de normalización del teléfono de su implementación para borrar el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores Lync Server 2013. Si no encuentra el archivo, cree un archivo vacío con el nombre "Company\_Phone\_Number\_Normalization\_Rules.txt".

5.  Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores Lync Server 2013 de la implementación.
    
        Update-csAddressBook

## El servidor de libreta de direcciones genera el evento de error 21054 una vez por día para cada grupo de servidores Lync 2013 (3195918)

**Problema:**

El servidor de libreta de direcciones de Lync Server 2013 genera el evento de error 21054 una vez por día al realizar las tareas de mantenimiento diarias. El error también se genera cada vez que un administrador ejecuta el cmdlet **Update-csAddressBook**, incluso cuando la actualización se realiza correctamente. En dicho caso, el evento de error se puede omitir sin problemas.

**Solución alternativa:**

Cuando detecta este evento de error, ejecute el siguiente cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si el cmdlet notifica que no hay objetos no indizados o abandonados, el evento de error 21054 se puede omitir sin problemas.

Además, se debe desactivar el indicador clave de estado (KHI) de los usuarios de libreta de direcciones indizados correctamente en System Center Operations Manager.

## Es posible que las solicitudes presenten errores cuando se configura IPv6 en un grupo de servidores perimetrales (3205810)

**Problema:**

Cuando se configura IPv6 en un grupo de servidores perimetrales, es posible que algunas solicitudes enviadas al grupo presenten errores.

**Solución alternativa:**

Para solucionar este problema, no configure IPv6 en un grupo de servidores perimetrales.

## El cmdlet invoke-csPoolFailback puede presentar errores durante la conmutación por recuperación del grupo de servidores (3206153)

**Problema:**

Al intentar la conmutación por recuperación de un grupo de servidores, el cmdlet **invoke-csPoolFailback** puede generar un error que indica que no se pudo al completar el proceso de hidratación tras varios intentos.

**Solución alternativa:**

Para solucionar este problema, ejecute el cmdlet de nuevo y espere hasta que se complete correctamente. Tenga en cuenta que el proceso de conmutación por recuperación puede tardar varios minutos en completarse. Puede tardar hasta 60 minutos para un grupo de servidores con 20.000 usuarios.

## Es posible que se pierdan datos al agregar un Servidor front-end a un grupo de servidores ya establecido (3015990) – Híbrido, Skype Empresarial Online

**Problema:**

Puede detectar este problema cuando un entorno tiene un grupo con más de un Servidor front-end, y se reinicia uno de los Servidores front-end o se agrega un Servidor front-end nuevo que no formaba parte del grupo anteriormente.

Los usuarios que tienen datos para archivar pueden sufrir pérdidas de datos hasta que se establezca una distribución estable del archivado para el grupo de servidores. Este período de posibles pérdidas de datos está limitado a 15 minutos para las conversaciones entre personas y a 30 minutos para las conferencias.

**Solución alternativa:**

Al realizar tareas de mantenimiento, en lugar de iniciar los Servidores front-end del grupo uno por uno, debe realizar la conmutación por error del grupo a otro grupo y luego realizar las tareas de mantenimiento en los servidores. También puede interrumpir el servicio antes de realizar las tareas de mantenimiento y luego restaurar su disponibilidad una vez completadas las tareas.

## Los administradores no pueden obtener el número de licencias con el cmdlet Get-CsClientAccessLicense (3012255)

**Problema:**

Los administradores no pueden obtener el uso exacto de licencias de cliente con el cmdlet **Get-CsClientAccessLicense**.

**Solución alternativa:**

Para comprobar el tipo de licencia del servidor, puede ejecutar el cmdlet **Get-CsService** para recuperar los nombres de dominio completos (FQDN) de todas las bases de datos. Si el FQDN del Servidor front-end es igual al FQDN de la base de datos back-end, la licencia es de un servidor Standard Edition. En caso contrario, la licencia será de un servidor Enterprise Edition.

## El número de licencias de cliente no se refleja con exactitud (3010175)

**Problema:**

Al determinar el número de licencias de cliente, es posible que se produzcan las siguientes condiciones:

1.  **Número impreciso de licencias para usuarios móviles**
    
    El número de licencias se basa en el número de direcciones IP únicas para los usuarios de dispositivos. El número de licencias estará limitado de las siguientes maneras:
    
      - El número de licencias será superior al real si la dirección IP del usuario se modifica durante las sesiones de Lync. Esto puede suceder cuando un usuario se conecta a Lync Server desde más de una ubicación con un cliente de escritorio.
    
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

**Solución alternativa:**

1.  **Número impreciso de licencias para usuarios móviles**
    
      - Puede identificar manualmente las direcciones IP que pertenecen al mismo dispositivo y luego quitar una de ellas del número de licencias.
    
      - No existe ninguna solución para este problema con los dispositivos móviles que se conectan a un cliente de Lync.

2.  **Las licencias se cuentan dos veces para las llamadas RTC al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync desviadas a las líneas RTC**
    
    Deberá identificar manualmente el número de teléfono RTC y quitar el número de licencias generado para él.

3.  **No se contará ninguna licencia para un teléfono Lync conectado**
    
    Puede configurar el teléfono Lync para que cierre la sesión y vuelva a iniciarla, a un intervalo regular, por ejemplo, cada tres meses.

4.  **Licencias consideradas para teléfonos RTC que se unen a conferencias**
    
    Puede identificar manualmente el número de teléfono RTC que se usa para unirse a la conferencia y quitar la licencia generada por el número de teléfono.

## El Panel de control de Lync Server deja de funcionar en un entorno VMware tras la actualización a Silverlight 5 (3010077)

**Problema:**

Si usa el Panel de control de Lync Server en un entorno VMware, es posible que el Panel de control de Lync Server deje de funcionar tras actualizar Microsoft Silverlight a la versión 5.

**Solución alternativa:**

Para solucionar este problema, siga uno de estos procedimientos:

  - Desinstale Silverlight 5 e instale Silverlight 4 desde [http://go.microsoft.com/fwlink/p/?LinkID=149156](http://go.microsoft.com/fwlink/p/?linkid=149156).

  - Obtenga acceso al Panel de control de Lync Server desde un equipo que no sea un equipo virtual VMware.
    
    Para ello, puede iniciar el Panel de control de Lync Server desde el menú **Inicio** de Windows en el servidor, si se instalaron las herramientas de administración de Lync Server en el equipo.
    
    También puede obtener acceso al Panel de control de Lync Server con un explorador web. La dirección URL será similar a https://\<fqdn\_grupo\_servidores\_frontend\>/cscp.

## La información de usuario del servicio de libreta de direcciones no se actualiza una vez que se modifica el nombre distintivo del usuario en Active Directory (3211549)

**Problema:**

Si el nombre distintivo (DN) de un usuario se modifica en Servicios de dominio de Active Directory, todos los cambios que se realicen además de esa modificación no se actualizarán en el servicio de libreta de direcciones (ABS). Esto no afectará al inicio de sesión ni a la presencia del usuario, pero impedirá la comunicación del usuario si se modifica también la dirección SIP, ya que las búsquedas devolverán una dirección SIP obsoleta.

**Solución alternativa:**

Para solucionar este problema, no modifique el DN de un usuario. Si revierte el DN del usuario al valor anterior, las actualizaciones se reflejarán en el servicio de libreta de direcciones.

## Instalación

## El uso de caracteres que no son ASCII puede hacer que el servidor Lync empiece a fallar

**Problema:**

La instalación generará errores si el nombre de la carpeta de destino incluye caracteres que no son ASCII (incluido UNICODE, el conjunto de caracteres de doble byte (DBCS), UTF-8 y UTF-16). Además, la instalación puede ser correcta, pero el servidor no se iniciará si hay caracteres que no son ASCII en cualquiera de las siguientes opciones:

  - Nombre de equipo

  - Nombre de dominio

  - Nombre de usuario

  - URI del SIP de usuario

  - Nombre de cuenta de servicio

**Solución alternativa:**

Utilice solo caracteres ASCII en el nombre de la carpeta de destino, el nombre de equipo, el nombre de dominio, el nombre de usuario, el URI del SIP de usuario y la cuenta de servicio.

## Antes de instalar Lync Server 2013, se debe instalar la revisión para los daños en el montón cuando un módulo llama al método InsertEntityBody en IIS 7.5

**Problema:**

Antes de instalar Lync Server 2013, se debe instalar la revisión para “Daños en el montón cuando un módulo llama al método InsertEntityBody en IIS 7.5” ([http://go.microsoft.com/fwlink/p/?LinkId=268602](http://go.microsoft.com/fwlink/p/?linkid=268602)) que se describe en el artículo 264886 de Microsoft Knowledge Base ([http://go.microsoft.com/fwlink/p/?LinkId=268603](http://go.microsoft.com/fwlink/p/?linkid=268603)).

**Solución alternativa:**

Descargue e instale la revisión desde el Centro de descarga de Microsoft en [http://go.microsoft.com/fwlink/?linkid=268602\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268602%26clcid=0xc0a).

## No se puede instalar Lync Server 2013 en ITA Windows Server 2012 versión RTM (3179467)

**Problema:**

No se puede instalar Lync Server 2013 en ITA Windows Server 2012 debido a un error de instalación de Windows Fabric.

Se produce un error al instalar Windows Fabric porque se crean seguimientos de tejidos con el formato de hora HH:MM:SS. Sin embargo, en ITA Windows Server, el formato de hora es HH.MM.SS.

**Solución alternativa:**

Para solucionar este problema, actualice el Registro del sistema antes de instalar Lync Server 2013. La clave del Registro que se debe actualizar es: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat. Cambie el valor de sTimeFormat a HH:mm:ss con la Interfaz de la línea de comandos Windows PowerShell de esta manera:

1.  Abra Windows PowerShell y ejecute los siguientes cmdlets:
    
    ```
    New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
    ```
    ```
    $a="HKU:\.Default\Control Panel\International"
    ```

2.  Para ver el valor actual, ejecute el siguiente cmdlet:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Anote el valor actual de sTimeFormat para poder restaurarlo una vez finalizada la instalación.

3.  Para establecer un nuevo valor, ejecute el siguiente cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Una vez que Lync Server 2013 se instaló correctamente, ejecute el siguiente cmdlet para restaurar el valor original de sTimeFormat:
    
        - Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3. above>"

## Movilidad

## Problemas de clientes móviles durante el proceso de conmutación por error del servidor (3345992)

**Problema:**

Cuando un servidor Lync deja de funcionar correctamente y comienza el proceso de conmutación por error, pueden afectar a los usuarios de clientes móviles los siguientes problemas:

  - No se recibe ninguna señal ni llamada de Lync entrante hasta 10 minutos después de comenzar la conmutación por error, como máximo.

  - No se pueden aceptar solicitudes de chat entrantes

  - Si el servidor que dejó de funcionar era el servidor principal del usuario, no se puede unir a ninguna reunión

**Solución alternativa:**

No hay solución alternativa para este problema. La funcionalidad habitual se restaurará cuando haya finalizado el proceso de conmutación por error.

## Si un usuario móvil rechaza una llamada entrante proveniente de otro extremo de Lync, la llamada se muestra como una conversación perdida en los clientes de Lync Mobile (3346251)

**Problema:**

Si un usuario móvil rechaza una llamada entrante, y la llamada se originó en otro extremo de Lync, la llamada se muestra como una conversación perdida en el cliente de Lync Mobile, en lugar de mostrarse como llamada en la lista de llamadas del dispositivo.

**Solución alternativa:**

No hay solución alternativa para este problema.

## Es posible que el cliente móvil no muestre el nombre para mostrar de un contacto federado al buscar contactos (3346256)

**Problema:**

Es posible que el nombre para mostrar de los contactos federados no se muestre en algunos escenarios: por ejemplo, al buscar un contacto federado en la lista de contactos. Esto puede ocurrir cuando no hay ninguna suscripción de presencia activa para el contacto desde el cliente móvil de Lync.

**Solución alternativa:**

No hay solución alternativa para este problema.

## En el cliente móvil, falta la información de invitado y marca de tiempo en las conversaciones perdidas que son invitaciones a conferencias (3346265)

**Problema:**

En el cliente móvil, cuando una conversación perdida es una invitación a una conferencia, falta la información de invitado y marca de tiempo en el mensaje de conversación perdida.

**Solución alternativa:**

No hay solución alternativa para este problema.

## Los usuarios de clientes móviles que realizan llamadas mediante VoIP no pueden dejar correo de voz a los usuarios cuyo correo de voz está configurado en Exchange 2010 o versiones anteriores (3346260)

**Problema:**

Si un usuario de cliente móvil utiliza VoIP para realizar llamadas, el usuario no podrá dejar mensajes de correo de voz a los usuarios configurados para usar correo de voz en Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.

**Solución alternativa:**

Como solución alternativa a este problema, puede utilizar Exchange 2010 con SP1 o una versión posterior de Microsoft Exchange Server.

## Al usar Bloquear con dirección URL en la Configuración de versión de cliente de los clientes móviles, puede que se muestre un mensaje de error incorrecto (3346258)

**Problema:**

Al usar **Bloquear con dirección URL** en la Configuración de versión de cliente de los clientes móviles, puede que se muestre un mensaje de error incorrecto si la versión del cliente no se admite.

**Solución alternativa:**

Como solución alternativa a este problema, puede configurar la Configuración de versión de cliente de modo que use **Bloquear** en lugar de **Bloquear con dirección URL**.

## Conferencia

## El software antivirus que se ejecuta en los Servidores front-end de Lync Server 2013 puede provocar el reciclado del dominio de aplicación, que interrumpe temporalmente el servicio para los clientes de Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013 (3212531)

**Problema:**

El software antivirus puede desencadenar un reinicio del dominio de aplicación, lo que puede provocar que las aplicaciones cliente de API web de comunicaciones unificadas (UC) y Lync Mobility Service 2013 ( Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013) pierdan su estado.

**Solución alternativa:**

Para solucionar este problema, excluya las carpetas que contienen componentes web y .NET Framework del análisis antivirus. Para más información, vea el artículo 312592 de Microsoft Knowledge Base, "PRB: reinicio de aplicación aleatoria con error 'Se está reiniciando la aplicación' en ASP.NET", en [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a).

Se deben excluir las siguientes carpetas:

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext

  - %Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config

## Los controles ActiveX o la compatibilidad con XMLHTTP nativo se deben habilitar en Windows Internet Explorer para unirse correctamente a las conferencias (2798163)

**Problema:**

Si un usuario deshabilitó los controles ActiveX y la compatibilidad con XMLHTTP nativo en la configuración del explorador Windows Internet Explorer, el usuario no podrá unirse a una reunión si se seleccionó Internet Explorer como explorador predeterminado.

**Solución alternativa:**

Habilite los controles ActiveX o la compatibilidad con XMLHTTP nativo en Internet Explorer.

## El servicio de conferencia web de Lync Server no se puede recuperar del modo crítico (2788663)

**Problema:**

Si el modo crítico está activado para el archivado, en caso de errores del sistema, se iniciará el modo crítico y las conferencias ya no funcionarán para los participantes. Una vez que el administrador corrige los errores del sistema (por ejemplo, un problema en la base de datos), el servicio de conferencia de datos no se recupera de manera automática, y el administrador debe reiniciar el servicio manualmente para reanudar las conferencias.

**Solución alternativa:**

El administrador debe reiniciar manualmente el servicio de conferencia una vez que se corrige el error del sistema.

## El servicio de conferencia web omite el proxy HTTP de los servidores de Office Web App externos (2602182)

**Problema:**

Si implementó un Servidor Office Web Apps externo al servicio de conferencia web (es decir, un servidor que no está en la red corporativa interna) en la red perimetral, en Internet, y el servicio de conferencia web requiere un proxy HTTP para conectarse, se generará un error en la detección del Servidor Office Web Apps. El servicio de conferencia web omite la configuración del proxy HTTP, como se define en el Generador de topologías para la configuración de Servidor Office Web Apps. Como resultado, el cliente de Lync no podrá compartir contenido de Microsoft PowerPoint 2010 con otros participantes de la conferencia. Si desea instalar Lync Server de manera local y además desea configurar el Servidor Office Web Apps de manera local en la red interna, no se necesita una configuración de proxy.

**Solución alternativa:**

La única solución es no contar con una configuración de implementación que requiera el uso del proxy HTTP para comunicarse con un Servidor Office Web Apps externo.

## No es posible agregar vídeo a una conferencia de un proveedor de servicios de audioconferencia (2603861)

**Problema:**

No es posible agregar un vídeo si el usuario se unió a una conferencia de un proveedor de servicios de audioconferencia.

**Solución alternativa:**

No hay solución alternativa para este problema.

## Las topologías con IPv6 habilitado fuerzan la actualización automática del complemento Silverlight de Lync Web App para garantizar que la función de uso compartido de la pantalla pueda funcionar en Lync Web App (2604634)

**Problema:**

Cuando se configura una topología con IPv6 habilitado, los usuarios no pueden compartir su pantalla desde el cliente de Lync Web App si ya hay instalada una versión anterior del complemento de uso compartido de la pantalla.

**Solución alternativa:**

Para forzar una actualización a la versión más reciente del complemento de uso compartido de la pantalla al unirse a una reunión a través de Lync Web App, modifique el valor de **MinSupportedBuildVersion** de "4.0.7457.0" a "4.0.7577.380" en los dos archivos siguientes:

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml

## Telefonía IP empresarial

## En algunos casos, es posible que los clientes de Lync que se ejecuten en equipos configurados para usar doble pila IPv4 e IPv6 no admitan la funcionalidad que depende de la subred IP del equipo, como E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en ubicación (3335508)


> [!NOTE]
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



**Problema:**

Cuando un cliente de Lync se ejecuta en un equipo habilitado para doble pila IPv4 e IPv6 y basado en la resolución DNS del servidor proxy, puede que el cliente use la dirección IPv6 del equipo para iniciar sesión. Después de hacerlo, el cliente de Lync solo admitirá la funcionalidad admitida en IPv6, en la que no están incluidos E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en ubicación.

**Solución alternativa:**

Como solución alternativa a este problema, puede deshabilitar la compatibilidad con IPv6 en el equipo cliente.

## Si no se configuró Telefonía IP empresarial para un usuario, el usuario deberá usar el formato E164 para realizar llamadas salientes desde una conferencia (3215342)

**Problema:**

Si no se configuró Telefonía IP empresarial para un usuario, el usuario deberá usar el formato E164 para realizar llamadas salientes desde una conferencia. Si no se usa el formato E164, el usuario no podrá realizar llamadas salientes desde la conferencia.

**Solución alternativa:**

Para solucionar este problema, los usuarios que no están habilitados para Telefonía IP empresarial deben usar números con el formato E164 para realizar llamadas salientes desde una conferencia.

## Presencia

## Si un usuario seleccionó "Bloquear todas las invitaciones y comunicaciones" cuando el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería (3204526)

**Problema:**

Si un usuario seleccionó "Bloquear todas las invitaciones y comunicaciones" cuando el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería.

**Solución alternativa:**

Para solucionar este problema, puede desactivar el almacén de contactos unificado para el usuario. Para ello, ejecute los siguientes cmdlets:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Por ejemplo:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

## Los usuarios de Office Communications Server 2007 R2 hospedados en implementaciones locales no pueden ver el estado de presencia de los usuarios de Skype Empresarial Online en implementaciones híbridas (3014624) – Híbrido

**Problema:**

Este problema se puede presentar en una implementación híbrida cuando usa un director de Lync Server 2013.

El estado de presencia de los usuarios hospedados en Skype Empresarial Online aparece como "Presencia desconocida" para los usuarios locales. Además, los usuarios hospedados en Skype Empresarial Online no pueden ver el estado de presencia de los usuarios locales de Office Communications Server R2.

**Solución alternativa:**

Para solucionar este problema de manera parcial, cambie el servidor principal (msrtcsip-presencehomeserver) de los usuarios de Skype Empresarial Online para que hagan referencia a un grupo de servidores Lync Server 2013 locales en lugar del director de Lync Server 2013. Puede modificar esta configuración en el Servidor front-end local.

Esta solución mostrará correctamente el estado de presencia de los usuarios hospedados en Office Communications Server 2007 R2 para los usuarios de Skype Empresarial Online.

## Aplicación de grupo de respuesta, Aplicación de estacionamiento de llamadas y atención de llamadas grupales

## Puede que el autor de la llamada escuche un segundo de música en espera durante el establecimiento de una llamada con quien recupera la llamada (3334097)


> [!NOTE]
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



**Problema:**

Cuando se recupera una llamada mediante la atención de llamadas grupales, puede que el autor de la llamada escuche un segundo de música en espera durante el establecimiento de la llamada con quien recupera la llamada.

**Solución alternativa:**

No hay solución alternativa para este problema.

## Un agente de Grupo de respuesta puede iniciar y cerrar una sesión a través de la consola de agente de Lync Server 2010 solo en grupos de agentes formales de Lync Server 2010 (2773455)

**Problema:**

Un agente de Grupo de respuesta de Lync Server 2013 puede iniciar y cerrar una sesión a través de la consola de agente de Lync Server 2010 solo en grupos de agentes formales de Lync Server 2010. En la consola de agente de Lync Server 2010, los usuarios solo pueden ver el Grupo de respuesta de Lync Server 2010 al que pertenecen. No pueden ver ninguno de los grupos de respuestas de Lync Server 2013 a los que pertenecen.

**Solución alternativa:**

Si el agente de Grupo de respuesta es un usuario de Lync Server 2013 y forma parte de un grupo de agentes formal de Lync Server 2013, el usuario debe tener acceso a la consola de agente de Lync Server 2013 directamente a través de un vínculo web de un explorador para iniciar y cerrar una sesión en los grupos de agentes de Lync Server 2013.

## Un agente de Grupo de respuesta de Lync Server 2010 no puede realizar llamadas en nombre de un Grupo de respuesta de Lync Server 2013 (2773471)

**Problema:**

Un usuario de Lync Server 2010 que es agente de un Grupo de respuesta de Lync Server 2013 no puede realizar una llamada en nombre del Grupo de respuesta. El Grupo de respuesta de Lync Server 2013 no estará disponible en el cliente de Lync para realizar una llamada.

**Solución alternativa:**

Para solucionar este problema, debe mover el usuario de Lync Server 2010 a Lync Server 2013.

## Al quitar un Grupo de respuesta de Lync Server 2010 tras la migración a Lync Server 2013, el Grupo de respuesta no podrá aceptar llamadas entrantes (3016227)

**Problema:**

Si un Grupo de respuesta que se ha migrado de Lync Server 2010 a Lync Server 2013 se quita de Lync Server 2010 a través del Panel de control de Lync Server o el Shell de administración de Lync Server, el Grupo de respuesta de Lync Server 2013 dejará de recibir llamadas entrantes.

**Solución alternativa:**

Para solucionar este problema, no quite ningún grupo de respuesta de Lync Server 2010 que se haya migrado de Lync Server 2010 a Lync Server 2013.

Si ya se quitó el Grupo de respuesta, debe volver a implementarlo en Lync Server 2013.

## Cuando un nuevo flujo de trabajo administrado se establece en inactivo al crearse, se producirá un error al implementar el flujo de trabajo (3207527)

**Problema:**

Cuando un nuevo flujo de trabajo administrado se establece en inactivo al crearse, se producirá un error al implementar el flujo de trabajo. Este problema se detecta cuando el flujo de trabajo se establece en inactivo al crearse, pero no afecta a un flujo de trabajo que se modifica para establecerse en inactivo después de su implementación.

**Solución alternativa:**

Al crear e implementar un flujo de trabajo, establezca el flujo de trabajo como activo y luego impleméntelo. Una vez que se implementa correctamente, el flujo de trabajo se puede modificar y establecer en inactivo.

## Al quitar un Grupo de respuesta del grupo de servidores propietario, el Grupo de respuesta del grupo de servidores de reserva no podrá aceptar llamadas entrantes durante la conmutación por error si el Grupo de respuesta se importó al grupo de servidores de reserva (3016214)

**Problema:**

Si un Grupo de respuesta, que es propiedad del grupo de servidores principal, se importó al grupo de servidores de reserva sin sobrescribir el propietario y el Grupo de respuesta se quita del grupo de servidores propietario, el grupo de respuesta del grupo de servidores de reserva no aceptará llamadas entrantes durante la conmutación por error.

**Solución alternativa:**

Deberá volver a implementar el Grupo de respuesta en el grupo de servidores principal. Luego, deberá exportar la configuración del Grupo de respuesta del grupo de servidores principal e importarla de nuevo en el grupo de servidores de reserva.

También puede volver a crear el Grupo de respuesta en el grupo de servidores de reserva. En este caso, el grupo de servidores de reserva será el grupo de servidores propietario del Grupo de respuesta.

## Una llamada estacionada no se puede recuperar de la Aplicación de estacionamiento de llamadas si la solicitud de recuperación se realiza en nombre de un Grupo de respuesta (3211798)

**Problema:**

Cuando se cumplen las siguientes condiciones, se producirá un error en la solicitud de recuperación de una llamada estacionada:

  - Un agente forma parte de un Grupo de respuesta anónimo

  - El agente intenta recuperar una llamada estacionada de la Aplicación de estacionamiento de llamadas a través del Grupo de respuesta anónimo

  - El agente intenta recuperar la llamada marcando el número de órbita con la opción de llamada en nombre de un grupo de respuesta o con la misma opción en el cliente de Lync Attendant

**Solución alternativa:**

No existen soluciones para este problema. La llamada estacionada se debe recuperar sin hacerlo en nombre de un Grupo de respuesta.

## Panel de control de Lync Server, Generador de topologías y Herramienta de planeación

## Limitaciones de Planning Tool (3331056 y 3331059)


> [!NOTE]
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



**Problema:**

Planning Tool tiene las siguientes limitaciones al planear la implementación:

  - Se admiten 10 sitios centrales como máximo

  - Cada sitio central puede tener 14 sitios de sucursal como máximo

  - Cada sitio central puede tener 240 000 usuarios como máximo

Además, Planning Tool no incluye los valores de los siguientes elementos al calcular la topología recomendada:

  - El número de usuarios alojados en línea

  - El porcentaje de usuarios habilitados para la federación XMPP

  - El porcentaje de usuarios que utilizan Lync Web App

**Solución alternativa:**

No hay solución alternativa para estos problemas. Para obtener más información sobre Planning Tool, consulte [Diseño de la topología para Lync Server 2013 con la herramienta de planeación](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

## Es posible que Planning Tool no utilice las direcciones IP definidas anteriormente para la red perimetral al actualizar las opciones

**Problema:**

Después de completar el diseño con Planning Tool, si realiza cambios en las opciones de la red perimetral, puede que se agreguen al diseño direcciones IP adicionales, en lugar de actualizarse las direcciones IP existentes. Esto puede ocurrir cuando, al ver los detalles del diagrama de red perimetral, elige **Haga clic aquí para actualizar las opciones** y, luego, en el diálogo Opciones de configuración, elige Red perimetral y **Quiero usar los mismos FQDN y las mismas direcciones IP, pero puertos diferentes para los servicios perimetrales en mi servidor perimetral** . Al aplicar cualquier cambio, se agregarán al diseño direcciones IP y servidores perimetrales nuevos.

**Solución alternativa:**

Actualmente, no hay ninguna solución alternativa para este problema.

## En el Panel de control de Lync Server, es posible que "Mover todos los usuarios al grupo" no funcione del modo esperado (3199270)

**Problema:**

Al usar el Panel de control de Lync Server para mover todos los usuarios de un grupo de servidores a otro en un entorno complejo de Active Directory, por ejemplo, uno con varios controladores de dominio y dominios primario/secundarios, es posible que aparezca un mensaje de error que indique lo siguiente: "El usuario especificado no es un usuario heredado. Use en su lugar el cmdlet Move-CsUser". Esto se debe a que los tiempos de replicación son mayores en los entornos complejos de Active Directory.

**Solución alternativa:**

Para solucionar este problema, siga uno de estos procedimientos:

  - Use los filtros del Panel de control de Lync Server para buscar usuarios heredados, seleccione esos usuarios y luego use el comando **Mover usuarios seleccionados a grupo** en lugar de **Mover todos los usuarios al grupo** .

  - Use el Shell de administración de Lync Server para mover usuarios heredados en lotes con los cmdlets de Lync Server.

## El Panel de control de Lync Server deja de funcionar en un entorno VMware tras actualizar Complemento de explorador Microsoft Silverlight a la versión 5 (3199270)

**Problema:**

Si usa el Panel de control de Lync Server en un entorno VMware, es posible que el Panel de control de Lync Server deje de funcionar tras actualizar Silverlight a la versión 5.

**Solución alternativa:**

Para solucionar este problema, siga uno de estos procedimientos:

  - Desinstale Silverlight 5 y luego instale Silverlight 4 desde [http://go.microsoft.com/fwlink/?linkid=149156\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=149156%26clcid=0xc0a).

  - Abra el Panel de control de Lync Server en un equipo que no sea un equipo virtual VMware.
    
    Para abrir el Panel de control de Lync Server desde un equipo remoto, instale las herramientas de administración de Lync Server en el equipo y luego inicie el Panel de control de Lync Server desde el menú **Inicio** de Windows.
    
    También puede abrir el Panel de control de Lync Server escribiendo la dirección URL en un explorador web. La dirección URL será similar a https://\<fqdn\_grupo\_servidores\_frontend\>/cscp.

## Un administrador no puede ejecutar el cmdlet Uninstall-csMirrorDB tras quitar la base de datos reflejada en el Generador de topologías (3199266)

**Problema:**

Cuando un administrador deshabilita una base de datos reflejada en el Generador de topologías y luego elimina esa base de datos en el Generador de topologías, aparece un mensaje en la lista de tareas pendientes para que el administrador ejecute el cmdlet **Uninstall-csMirrorDatabase** a fin de quitar el reflejo de SQL Server. Cuando el administrador intenta ejecutar el cmdlet, se produce un error.

**Solución alternativa:**

Para quitar el reflejo de SQL de un grupo en el Generador de topologías, primero debe usar un cmdlet para quitar el reflejo en SQL Server. Luego, puede usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo en SQL Server, use el siguiente cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por ejemplo, para quitar el reflejo y descartar las bases de datos de usuario, escriba lo siguiente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

El parámetro *DropExistingDatabasesOnMirror* hace que las bases de datos afectadas se eliminen del reflejo. Luego, para quitar el reflejo de la topología, haga lo siguiente:

1.  En el Generador de topologías, haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades** .

2.  Desactive **Habilitar creación de reflejo de almacén SQL** y haga clic en **Aceptar** .

3.  Publique la topología.

> [!IMPORTANT]  
> Cada vez que haga un cambio en una relación de creación de reflejo de la base de datos back-end, debe reiniciar todos los Servidores front-end del grupo.



## Se devuelven errores de validación en el Generador de topologías cuando un administrador intenta quitar una implementación con un grupo de servidores front-end que tiene un almacén de testigos asociado (3199266)

**Problema:**

Si un administrador intenta usar el comando **Quitar implementación** en el Generador de topologías para quitar una implementación que incluye un grupo de servidores front-end con un almacén de testigos asociado, aparece un error de validación en el Generador de topologías y la acción no continuará.

**Solución alternativa:**

Para solucionar este problema, siga uno de estos procedimientos:

  - Quite el almacén de testigos antes de tratar de quitar la implementación.

  - Agregue un almacén de testigos para el grupo de servidores front-end y luego quítelo.

## La información de la implementación del Servidor de chat persistente no es coherente entre la Herramienta de planeación y el Generador de topologías (3012228)

**Problema:**

Cuando la Lync Server 2013, herramienta de planeación produce el diagrama de topología del sitio para una implementación del Servidor de chat persistente con la recuperación ante desastres habilitada, el diagrama de topología del sitio incluye varios sitios (físicos), con Servidores de chat persistente asignados de manera uniforme en cada sitio. En el Generador de topologías, todos los Servidores de chat persistente se representan como si pertenecieran a un único sitio (lógico) y se muestran en el mismo nodo del Grupo de servidores de chat persistente.

**Solución alternativa:**

Actualmente, no existe ninguna solución para este problema. El usuario debe analizar el resultado de la Herramienta de planeación para la implementación del Servidor de chat persistente y modificar el plan para que cumpla con sus necesidades específicas.

## Localización

## Supervisión

## El Asistente para implementar informes del servidor de supervisión muestra caracteres incorrectos en determinados casos cuando se usa la versión de Asia Oriental de Lync Server (3113565)

**Problema:**

Cuando se usa una versión de Asia Oriental de Lync Server 2013, por ejemplo, chino (simplificado), chino (tradicional), japonés o coreano, en un sistema operativo que no tiene la configuración regional del sistema definida en un idioma de Asia Oriental, el Asistente para implementar informes del servidor de supervisión mostrará signos de interrogación u otros caracteres en lugar de mensajes localizados.

**Solución alternativa:**

Para corregir este problema, defina la configuración regional del sistema operativo y de Lync Server 2013 en el mismo idioma y, de este manera, todos los mensajes se mostrarán correctamente.

## Panel de control de Lync Server

## En algunos casos, el primer elemento de la barra de navegación superior en una página del Panel de control de Lync Server desaparece cuando se hace clic en el último elemento de la barra de navegación superior (3158118)

**Problema:**

Existen tres casos conocidos en los que, al hacer clic en el último elemento de la barra de navegación superior en una página del Panel de control de Lync Server, desaparece el primer elemento de la barra de navegación superior:

  - En la versión en francés, en la página "Féderation et accès externe", desaparece el elemento "Stratégie d'accès externe" al hacer clic en "Partenaires fédérés XMPP".

  - En la versión en alemán, en la página "Clients", desaparece el elemento "Clientversionskonfiguration" al hacer clic en "Pushbenachrichtigungskonfiguration".

  - En la versión en ruso, en la página "Конфигурация сети", desaparece el elemento "Глобально" al hacer clic en "Маршрут региона".

**Solución alternativa:**

Para solucionar este problema, actualice la página del Panel de control de Lync Server en el explorador. La página se cargará en el explorador con todos los elementos de la barra de navegación superior visibles.

## Libreta de direcciones

## La indización de la libreta de direcciones no funciona del modo esperado en algunos idiomas (3336047)


> [!NOTE]
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



Si las propiedades de un usuario contienen un campo indizado y ese campo contiene solamente caracteres que no se pueden indizar, el usuario no aparecerá en las búsquedas que se realicen en la libreta de direcciones.

Los caracteres y las configuraciones regionales siguientes no se pueden indizar:

  - Caracteres de mayúsculas cirílicas, griegas y armenias

  - Caracteres de mayúsculas acentuadas

  - Tailandés

  - Lao

  - Birmano

  - Devanagari

  - Etiópico

  - Tibetano

  - Bangla

  - Gujarati

  - Telugu

  - Todas las demás escrituras índicas

## Lync Web App, Programador web y componentes web

## Es posible que la reserva de algunos idiomas en Programador web de Lync, Acceso telefónico, Iniciador de participación en reuniones, Administración de salones de chat persistentes y OCTab no funcione del modo esperado (3079700)

**Problema:**

Al seleccionar una configuración regional neutral en un explorador web (en Internet Explorer, por ejemplo, el nombre del idioma sin más especificaciones, como “Noruego \[no\]”) en lugar de una configuración regional que especifique el idioma, la escritura y la configuración regional (como “Noruego, Bokmål (Noruega) \[nb-NO\]”), es posible que se produzca un comportamiento de visualización inesperado de determinados idiomas en Programador web de Lync, Acceso telefónico, Iniciador de participación en reuniones, Administración de salones de chat persistentes y OCTab. Por ejemplo, es posible que los usuarios vean la página en inglés al seleccionar uno de los siguientes idiomas:

  - Noruego

  - Portugués

  - Serbio

**Solución alternativa:**

Si desea seleccionar un idioma con una configuración regional neutral, asegúrese siempre de agregar también el idioma con una configuración regional específica (con un script o código de país) como idioma adicional en la lista de preferencias de idioma del explorador.

## Algunos exploradores web no admiten totalmente las configuraciones regionales de azerí y uzbeko al usar Programador web de Lync, Acceso telefónico, Iniciador de participación en reuniones, Administración de salones de chat persistentes y OCTab (3336748)


> [!NOTE]
> La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.



**Problema:**

Al usar Internet Explorer 8 o Internet Explorer 9, si se establece como idioma del explorador el azerí (latino) o el uzbeko (latino), las páginas de Acceso telefónico e Iniciador de participación en reuniones se mostrarán en inglés o en el idioma preferido establecido en el explorador.

Al usar los exploradores Firefox o Chrome, si se establece como idioma del explorador el azerí (latino) o el uzbeko (latino), Lync Web App, el Programador web de Lync y RGS OCTab se mostrarán en inglés o en el idioma preferido establecido del explorador.

El explorador Safari no admite la configuración regional de uzbeko (latino).

**Solución alternativa:**

No existe ninguna solución alternativa para estos problemas.

## Falta la flecha de la lista desplegable para "Unirse a la reunión" en la versión en rumano de Lync Web App (3154899)

**Problema:**

Cuando un usuario de la versión en rumano de Lync Web App realiza los siguientes pasos, no se muestra la flecha de la lista desplegable para **Unirse a la reunión** :

1.  Seleccione **Recordar mis datos en este equipo** en la pestaña **General** .

2.  Seleccione la pestaña **Teléfono** .

3.  Haga clic en la lista desplegable para **Unirse a la reunión** .
    
    Los usuarios no verán la flecha que indica que hay más valores que la opción **Lync Web App** predeterminada, por ejemplo: **No unirse al audio** (en rumano, "Nu se asociaža la componenta audio") y **Nuevo número** " (en rumano, "Numar nou").

**Solución alternativa:**

Aunque no se muestre la flecha de esta lista desplegable, los usuarios pueden seleccionar de todos modos las opciones adicionales de la lista haciendo clic en el valor predeterminado.

## Al usar la versión en turco del Programador web de Lync, no es posible guardar una reunión cuando se usa la opción "Las personas que yo elija" en "Quién es moderador" (3169483)

**Problema:**

Al crear o modificar una reunión en la versión en turco del Programador web de Lync, no se admite la opción "Las personas que yo elija" en "Quién es moderador". Cuando se selecciona esta opción, no se puede guardar la reunión. En cambio, aparece un mensaje de error que indica que una o más personas no pueden convertirse en moderadores.

**Solución alternativa:**

Para solucionar este problema, los usuarios pueden usar la opción predeterminada "Personas de mi compañía" o cualquier otra opción, como "Solo el organizador" o "Todos, incluidas las personas de fuera de mi compañía". El organizador puede disminuir o aumentar el nivel de los participantes para establecer sus roles correctos más adelante, una vez que se hayan unido a la reunión.

Además, los usuarios que entienden otro idioma pueden cambiar la selección de idioma en el explorador. Pueden elegir uno de los otros 43 idiomas admitidos e intentar usar la opción "Las personas que yo elija".

## Derechos de autor

Este documento hace referencia a una versión preliminar de un producto de software que puede haber cambiado considerablemente antes del lanzamiento de la versión comercial definitiva. La información que contiene es propiedad confidencial de Microsoft Corporation. Dicha información se divulga conforme a un acuerdo de confidencialidad entre el destinatario y Microsoft. Este documento se proporciona con carácter informativo únicamente y Microsoft no otorga garantías expresas ni implícitas en él. La información contenida en este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a modificaciones sin previo aviso. El usuario asume todos los riesgos resultantes del uso de este documento. A menos que se indique lo contrario, las compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares y eventos mencionados en los ejemplos son ficticios. No se pretende indicar ni debe deducirse ninguna asociación con compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares o eventos reales. El cumplimiento de las leyes de derechos de autor aplicables es responsabilidad del usuario. Sin limitar los derechos de autor, ninguna parte de este documento puede ser reproducida, almacenada o introducida en un sistema de recuperación, ni transmitida, de ninguna forma ni por ningún medio (ya sea electrónico, mecánico, fotocopia, grabación o de otro tipo), con ningún propósito, sin autorización expresa y por escrito de Microsoft Corporation.

Microsoft puede ser propietario de patentes, solicitudes de patentes, marcas comerciales, derechos de autor u otros derechos de propiedad intelectual relacionados con el tema de este documento. Excepto cuando quede expresamente indicado en cualquier contrato de licencia de Microsoft, el suministro de este documento no le otorga ninguna licencia sobre dichas patentes, marcas comerciales, derechos de autor u otro tipo de propiedad intelectual.

© 2012 Microsoft Corporation. Todos los derechos reservados.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook y SQL Server son marcas comerciales o marcas registradas de Microsoft Corporation en los Estados Unidos y/o en otros países o regiones.

Todas las demás marcas comerciales pertenecen a sus respectivos propietarios.

