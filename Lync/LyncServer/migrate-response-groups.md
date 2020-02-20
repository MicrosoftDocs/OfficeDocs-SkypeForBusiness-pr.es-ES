---
title: Migrar los grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fb771f448fdb6bb155f80403b5b978a62f714e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar los grupos de respuesta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-23_

Una vez que los usuarios se han movido a grupos de servidores de Lync Server 2013, puede migrar los grupos de respuesta. Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Lync Server 2013. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.

<div>


> [!NOTE]  
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar. En concreto, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.



</div>

Antes de migrar los grupos de respuesta, debe haber implementado un grupo de servidores de 2013 de Lync Server que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> Puede crear nuevos grupos de respuesta 2013 de Lync Server en el grupo de Lync Server 2013 antes de migrar los grupos de respuesta heredados.



</div>

Para migrar grupos de respuesta de un grupo heredado a la versión 2013 de Lync Server, ejecute el cmdlet **Move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> El cmdlet de migración del grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.



</div>

Después de migrar los grupos de respuesta, debe usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron correctamente.

Al migrar grupos de respuesta, los grupos de respuesta de Lync Server 2010 no se quitan. Cuando administre grupos de respuesta después de la migración mediante el panel de control de Lync Server o el shell de administración de Lync Server, puede ver los grupos de respuesta de Lync Server 2010 y de Lync Server 2013. Solo debe aplicar actualizaciones a los grupos de respuesta 2013 de Lync Server. Los grupos de respuesta de Lync Server 2010 solo se conservan por motivos de reversión.

<div>


> [!WARNING]  
> Una vez que se haya completado la migración y se hayan creado los nuevos grupos de respuesta, el panel de control de Lync Server y el shell de administración de Lync Server mostrarán las versiones de Lync Server 2010 y Lync Server 2013 de cada grupo de respuesta. No use el panel de control de Lync Server o el shell de administración de Lync Server para quitar los grupos de respuesta 2010 de Lync Server. Si quita una, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta de Lync Server 2010 se quitarán cuando retire el grupo de servidores de Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores. También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración. Si se debe quitar un grupo de respuesta 2010 de Lync Server, puede restaurar los grupos de respuesta a partir de la copia de seguridad para que los grupos de respuesta de Lync Server 2013 vuelvan a ejecutarse.



</div>

Lync Server 2013 presenta una nueva característica de grupo de respuesta llamada **tipo de flujo de trabajo**. El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**. Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía.

Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.

El siguiente procedimiento para migrar configuraciones de grupo de respuesta presupone que tiene una relación de uno a uno entre los grupos de servidores heredados y los grupos de servidores de 2013 de Lync Server. Si tiene previsto consolidar o dividir grupos durante la migración y la implementación, debe planear el grupo de servidores heredado asignado a cada grupo de servidores de Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar configuraciones de grupo de respuesta

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Después de migrar los grupos de respuesta y los agentes al grupo de servidores de Lync Server 2013, la dirección URL que los agentes usan para iniciar y cerrar sesión es una dirección URL de Lync Server 2013 y está disponible en el menú **herramientas** . Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para comprobar la migración del grupo de respuesta mediante el Panel de control de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.

4.  En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se incluyen en la lista.

5.  Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Lync Server 2010 se incluyen en la lista.

6.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se incluyen en la lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Para comprobar la migración del grupo de respuesta mediante el shell de administración de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

3.  Realizar
    
        Get-CsRgsAgentGroup

4.  Compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se incluyen en la lista.

5.  Realizar
    
        Get-CsRgsQueue

6.  Compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.

7.  Realizar
    
        Get-CsRgsWorkflow

8.  Compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se incluyen en la lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

