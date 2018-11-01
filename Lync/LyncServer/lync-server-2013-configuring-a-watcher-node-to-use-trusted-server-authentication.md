---
title: "Configurar nodo monitor para utilizar la autenticación con servidores de confianza"
TOCTitle: "Conf. d’un nœud observateur pour l’util. de l’auth. des serveurs approuvés"
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48275050
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de un nodo monitor para utilizar la autenticación mediante servidores de confianza

 

_**Última modificación del tema:** 2012-10-22_

Si el PC del nodo de monitor se encuentra dentro de la red perimetral, con la autenticación de servidor de confianza puede reducir considerablemente los impuestos de administración para mantener un único certificado en lugar de varias contraseñas de cuentas de usuario.

El primer paso para configurar la autenticación de servidor de confianza es crear un grupo de aplicaciones de confianza para alojar el PC del nodo de monitor. Después de haber creado el grupo de aplicaciones de confianza, debe configurar las transacciones sintéticas en ese nodo de monitor para que se ejecuten como una aplicación de confianza.


> [!NOTE]
> Una aplicación de confianza es una aplicación que se le concede el estado de confianza para ejecutarse como parte de Lync Server 2013, pero no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.



Para crear un grupo de aplicaciones de confianza, abra Shell de administración de Lync Server 2013 y ejecute un comando similar a este:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond


> [!NOTE]
> Para más información sobre los parámetros usados en el comando anterior, escriba lo siguiente en el símbolo del sistema de Shell de administración de Lync Server:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



Después de crear el grupo de aplicaciones de confianza, configure el PC del nodo de monitor para que ejecute las transacciones sintéticas como una aplicación de confianza. Esto se realiza con el cmdlet **New-CsTrustedApplication** y un comando similar a este:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Cuando finaliza el comando anterior y se haya creado la aplicación de confianza, ejecute Enable-CsTopology para asegurarse de que los cambios se han realizado:

    Enable-CsTopology

Después de ejecutar Enable-CsTopology, le recomendamos que reinicie el PC.

Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el símbolo del sistema de Shell de administración de Lync Server:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## Configuración de un certificado predeterminado en el nodo de monitor

Cada nodo de monitor debe tener un certificado predeterminado asignado mediante la Asistente para la implementación de Lync Server.

**Para asignar un certificado predeterminado**

1.  Haga clic en **Inicio**, **Todos los programas**, **Lync Server** y luego en **Asistente para la implementación de Lync Server**.

2.  En la Asistente para la implementación de Lync Server, haga clic en **Instalar o actualizar el sistema Lync Server** y luego en **Ejecutar** debajo del título **Solicitar, instalar o asignar certificados**.
    

    > [!NOTE]
    > Si el botón <STRONG>Ejecutar</STRONG> está deshabilitado, puede que primero necesite hacer clic en <STRONG>Ejecutar</STRONG> en <STRONG>Instalar el almacén de configuración local</STRONG>.



3.  Siga uno de estos procedimientos:
    
      - Si ya tiene un certificado que puede usarse como certificado predeterminado, haga clic en **Predeterminado** en el Asistente para certificados y luego haga clic en **Asignar**. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
      - Si necesita solicitar un certificado para usarlo como certificado predeterminado, haga clic en **Solicitar** y luego siga los pasos del Asistente para solicitar certificados para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.

## Instalación y configuración de un nodo de monitor

Después de haber reiniciado el PC del nodo de monitor y haber configurado un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode.msi en un PC donde estén instalados los archivos del agente de Operations Manager y los componentes principales Lync Server 2013).

**Para instalar y configurar un nodo de monitor**

1.  Abra el Shell de administración de Lync Server haciendo clic en **Inicio**, **Todos los programas**, **Lync Server** y luego en **Shell de administración de Lync Server**.

2.  En el Shell de administración de Lync Server, escriba el comando siguiente y presione ENTRAR (especifique la ruta de acceso real a la copia de Watchernode.msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    

    > [!NOTE]
    > También puede ejecutar Watchernode.msi desde una ventana de comandos. Para abrir una ventana de comandos, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y luego en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana de comandos, escriba el mismo comando anterior.



Nota que el par nombre-valor del anterior comando Authentication=TrustedServer distingue mayúsculas y minúsculas. Debe escribirlo exactamente como aparece. El siguiente comando tiene errores porque no usa las letras mayúsculas y minúsculas correctas:

C:\\Tools\\Watchernode.msi authentication=trustedserver

El modo TrustedServer solo se puede usar con los PC que se encuentran dentro de la red perimetral. Cuando un nodo de monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el PC.

