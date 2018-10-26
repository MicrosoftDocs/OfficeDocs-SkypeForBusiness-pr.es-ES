---
title: Migrar grupos de respuesta
TOCTitle: Migrar grupos de respuesta
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48275057
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar grupos de respuesta

 

_**Última modificación del tema:** 2013-09-23_

Después de que los usuarios se trasladan a los grupos de servidores de Lync Server 2013, puede migrar los grupos de respuesta. Migrar grupos de respuesta incluye copiar grupos de agente, colas, flujos de trabajo y archivos de audio, y trasladar los objetos de contacto de Grupo de respuesta desde la implementación heredada al grupo de servidores de Lync Server 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se manejan a través del Aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013. El grupo heredado ya no controla las llamadas a los grupos de respuesta.


> [!NOTE]
> Si bien puede migrar los grupos de respuesta antes de trasladar todos los usuarios al grupo de servidores de Lync Server 2013, recomendamos trasladar primero a todos los usuarios. En particular, los usuarios que son agentes del grupo de repuesta no podrán disponer de la funcionalidad completa de las nuevas características hasta que no se trasladen al grupo de servidores de Lync Server 2013.



Antes de migrar los grupos de respuesta, debe implementar un grupo de servidores de Lync Server 2013 que incluya el Aplicación de grupo de respuesta. El Aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la Telefonía IP empresarial. Para asegurarse de que el Aplicación de grupo de respuesta esté instalado, ejecute el cmdlet **Get-CsService –ApplicationServer**.


> [!NOTE]
> Puede crear grupos de respuesta de Lync Server 2013 nuevos en el grupo de servidores de Lync Server 2013 antes de migrar los grupos de respuesta heredados.



Para migrar grupos de respuesta de un grupo heredado a Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration**.

> [!IMPORTANT]  
> El cmdlet para la migración de Grupo de respuesta traslada la configuración de Grupo de respuesta de todo el grupo de servidores. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.



Después de migrar los grupos de respuesta, debe usar los cmdlets Panel de control de Lync Server o Shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se hayan trasladado correctamente.

Al migrar grupos de respuesta, no se quitan los grupos de respuesta de Lync Server 2010. Al administrar grupos de respuesta después de la migración con Panel de control de Lync Server o Shell de administración de Lync Server, puede ver los grupos de respuesta de Lync Server 2010 y los grupos de respuesta de Lync Server 2013. Debe aplicar actualizaciones solo a los grupos de respuesta de Lync Server 2013. Los grupos de respuesta de Lync Server 2010 se conservan solo con fines de reversión.

> [!CAUTION]  
> Tras completar la migración y crear los nuevos grupos de respuesta, el Panel de control de Lync Server y el Shell de administración de Lync Server mostrarán las versiones de Lync Server 2010 y Lync Server 2013 de cada grupo de respuesta. No use Panel de control de Lync Server o Shell de administración de Lync Server para quitar los grupos de respuesta de Lync Server 2010. Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta de Lync Server 2010 se quitarán después de retirar el grupo de Lync Server 2010.



> [!IMPORTANT]  
> Recomendamos que no quite ningún dato de la implementación anterior hasta retirar el grupo. Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración. Si se debe quitar un grupo de respuesta de Lync Server 2010, puede entonces restaurar los grupos de respuesta desde la copia de seguridad para volver a ejecutar los grupos de respuesta de Lync Server 2013.



Lync Server 2013 introduce una característica nueva de Grupo de respuesta denominada **tipo de flujo de trabajo**. El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**. Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía.

Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Sin embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.

El siguiente procedimiento para migrar las configuraciones de Grupo de respuesta supone que existe una relación uno a uno entre los grupos heredados y los grupos de Lync Server 2013. Si tiene previsto consolidar o dividir grupos de servidores durante la migración e implementación, debe planear qué grupo heredado asignar al grupo de servidores de Lync Server 2013.

## Migrar las configuraciones de Grupo de respuesta

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Después de migrar agentes y grupos de respuesta al grupo de Lync Server 2013, la dirección URL que usan los agentes para iniciar y cerrar sesión es una dirección URL de Lync Server 2013 y está disponible en el menú **Herramientas**. Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL.

## Para comprobar la migración del grupo de respuesta con Panel de control de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.

4.  En la pestaña **Flujo de trabajo**, compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se encuentran en la lista.

5.  Haga clic en la pestaña **Cola** y compruebe que todas las colas del entorno de Lync Server 2010 se encuentran en la lista.

6.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se encuentran en la lista.

## Para comprobar la migración del grupo de respuesta con Shell de administración de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.
    
    Para más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

3.  Ejecute:
    
        Get-CsRgsAgentGroup

4.  Compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se encuentran en la lista.

5.  Ejecute:
    
        Get-CsRgsQueue

6.  Compruebe que todas las colas del entorno de Lync Server 2010 se encuentran en la lista.

7.  Ejecute:
    
        Get-CsRgsWorkflow

8.  Compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se encuentran en la lista.

