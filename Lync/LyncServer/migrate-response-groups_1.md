---
title: Migrar grupos de respuesta
TOCTitle: Migrar grupos de respuesta
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48275389
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar grupos de respuesta

 

_**Última modificación del tema:** 2012-10-19_

Después de que los usuarios se trasladan a los grupos de Lync Server 2013, puede migrar los grupos de respuesta. La migración de los grupos de respuesta incluye la copia de grupos de agente, colas, flujos de trabajo y archivos de audio, y el traslado de los objetos de contacto de Grupo de respuesta desde la implementación heredada al grupo de Lync Server 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se manejan a través del Aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.


> [!NOTE]
> Si bien puede migrar los grupos de respuesta antes de trasladar todos los usuarios al grupo de servidores de Lync Server 2013, recomendamos trasladar primero a todos los usuarios. En particular, los usuarios que son agentes del grupo de repuesta no podrán disponer de la funcionalidad completa de las nuevas características hasta que no se trasladen al grupo de servidores de Lync Server 2013.



Antes de migrar los grupos de respuesta, debe implementar un grupo de servidores de Lync Server 2013 que incluya el Aplicación de grupo de respuesta. El Aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que el Aplicación de grupo de respuesta esté instalado, ejecute el cmdlet **Get-CsService–ApplicationServer**.


> [!NOTE]
> Puede crear grupos de respuesta de Lync Server 2013 nuevos en el grupo de servidores de Lync Server 2013 antes de migrar los grupos de respuesta heredados.



Para migrar grupos de respuesta desde un grupo heredado al Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration**. Antes de ejecutar el **Move-CsRgsConfiguration**, primero debe instalar el paquete de interfaces de Compatibilidad con versiones anteriores del Instrumental de administración de Windows (WMI). Instale esta aplicación al ejecutar OCSWMIBC.msi. Puede encontrar el archivo OCSWMIBC.msi en los medios de instalación en la carpeta de instalación.

> [!IMPORTANT]  
> El cmdlet para la migración de Grupo de respuesta traslada la configuración de Grupo de respuesta de todo el grupo de servidores. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.



Después de migrar los grupos de respuesta, debe actualizar la dirección URL que los agentes formales usan para iniciar y cerrar sesión en los grupos de respuesta, así como usar los cmdlets de Panel de control de Lync Server o Shell de administración de Lync Server para confirmar que todos los grupos de agentes, las colas y los flujos de trabajo se hayan trasladado correctamente.

> [!CAUTION]  
> Al migrar los grupos de respuesta, los grupos de respuesta de Office Communications Server 2007 R2 no se eliminan. No quite los grupos de respuesta de Office Communications Server 2007 R2. Si quita un grupo de respuesta de Office Communications Server 2007 R2, los de Lync Server 2013 dejarán de funcionar.



> [!IMPORTANT]  
> Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores. También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración. En caso de que un grupo de respuesta de Office Communications Server 2007 R2 se quite, se puede restaurar de la copia de seguridad para que los grupos de respuesta de Lync Server 2013 vuelvan a funcionar.



Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Sin embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.

> [!IMPORTANT]  
> Se recomienda no eliminar ningún dato los grupos de respuesta del grupo de servidores heredado hasta retirar dicho grupo de servidores.



El siguiente procedimiento para migrar las configuraciones de Grupo de respuesta asume que existe una relación uno a uno entre los grupos heredados y los grupos de Lync Server 2013. Si tiene previsto consolidar o dividir grupos de servidores durante la migración e implementación, debe planear qué grupo heredado asignar al grupo de servidores de Lync Server 2013.

## Para migrar configuraciones del Grupo de respuesta

1.  Busque OCSWMIBC.msi en la carpeta de instalación de los medios de instalación e instálelo.

2.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

3.  Abra Shell de administración de Lync Server.

4.  En la línea de comandos, escriba:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si ha implementado la pestaña Grupo de respuesta para Microsoft Office Communicator 2007 R2 en su entorno de Office Communications Server 2007 R2, quite la pestaña del archivo tabs.xml de Office Communicator 2007 R2.
    

    > [!NOTE]
    > Los agentes formales utilizaban la pestaña Grupo de respuesta para iniciar sesión en sus grupos de respuesta para así poder recibir llamadas. Si implementó la pestaña Grupo de respuesta, seleccionó la ubicación del archivo Office Communicator 2007 R2 cuando la implementó.



6.  Proporcione a los usuarios la dirección URL actualizada que los agentes necesitan para iniciar y cerrar sesión en sus grupos de respuesta.
    

    > [!NOTE]
    > Por lo general, la dirección URL tiene el formato https://FQDNgrupoweb/RgsClients/Tab.aspx, donde <EM>FQDNgrupoweb</EM> es el nombre de dominio completo (FQDN) del grupo de servidores web asociado con el grupo que recién migró a Lync Server 2013.

    

    > [!NOTE]
    > No es necesario realizar este paso una vez que los usuarios se actualizan a Lync 2013, ya que la URL está disponible en el menú <STRONG>Herramientas</STRONG> en Lync.



## Para comprobar la migración del grupo de respuesta mediante el Panel de control de Lync Server

1.  Abra Panel de control de Lync Server.

2.  En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.

3.  En la pestaña **Flujo de trabajo**, compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

4.  Haga clic en la pestaña **Cola** y compruebe que todas las colas del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

5.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

## Para comprobar la migración del grupo de respuesta mediante cmdlets

1.  Abra Shell de administración de Lync Server.
    
    Para más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

2.  En la línea de comandos, escriba:
    
        Get-CsRgsAgentGroup

3.  Compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

4.  En la línea de comandos, escriba:
    
        Get-CsRgsQueue

5.  Compruebe que todas las colas del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

6.  En la línea de comandos, escriba:
    
        Get-CsRgsWorkflow

7.  Compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se encuentran en la lista.

