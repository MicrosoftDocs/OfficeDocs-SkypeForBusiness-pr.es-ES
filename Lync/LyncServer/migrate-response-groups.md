---
title: Migrar grupos de respuesta
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
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar grupos de respuesta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-23_

Una vez que los usuarios se mueven a los grupos de Lync Server 2013, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contactos de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013. Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.

<div>


> [!NOTE]  
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar. En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.



</div>

Antes de migrar grupos de respuesta, debe haber implementado un grupo de 2013 de Lync Server que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Puede crear nuevos grupos de respuesta de Lync Server 2013 en el grupo de servidores de Lync 2013 antes de migrar los grupos de respuesta heredados.



</div>

Para migrar grupos de respuesta de un grupo heredado a Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar.



</div>

Después de migrar los grupos de respuesta, debe usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se han movido correctamente.

Al migrar grupos de respuesta, los grupos de respuesta 2010 de Lync Server no se quitan. Al administrar grupos de respuesta después de la migración mediante el panel de control de Lync Server o el shell de administración de Lync Server, puede ver los grupos de respuesta 2010 de Lync Server y los grupos de respuesta de Lync Server 2013. Solo debe aplicar actualizaciones a los grupos de respuesta 2013 de Lync Server. Los grupos de respuesta de Lync Server 2010 se conservan solo por motivos de reversión.

<div>


> [!WARNING]  
> Una vez completada la migración y creados los nuevos grupos de respuesta, el panel de control de Lync Server y el shell de administración de Lync Server mostrarán las versiones de Lync Server 2010 y Lync Server 2013 de cada grupo de respuesta. No use el panel de control de Lync Server ni el shell de administración de Lync Server para quitar los grupos de respuesta 2010 de Lync Server. Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta de Lync Server 2010 se quitarán al retirar el grupo de servidores de Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo. Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración. Si se debe quitar un grupo de respuesta 2010 de Lync Server, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 de nuevo.



</div>

Lync Server 2013 incorpora una nueva característica de grupo de respuesta denominada **tipo de flujo de trabajo**. El **tipo de flujo de trabajo** se puede administrar o **no administrar**. **** Todos los grupos de respuesta se migran con el **tipo de flujo de trabajo** establecido en **no administrado** y con una lista vacía de administrador.

Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación. Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado.

El siguiente procedimiento para migrar la configuración de un grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2013 de Lync Server. Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar las configuraciones de grupos de respuesta

1.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Después de migrar grupos de respuesta y agentes al grupo de servidores de Lync Server 2013, la dirección URL que los agentes usan para iniciar y cerrar sesión es una dirección URL de Lync Server 2013 y está disponible en el menú **herramientas** . Recuerde a los agentes que actualicen cualquier referencia, como marcadores, a la nueva dirección URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para comprobar la migración de grupos de respuesta mediante el panel de control de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.

4.  En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 están incluidos en la lista.

5.  Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.

6.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Lync Server 2010 están incluidos en la lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Para comprobar la migración de grupos de respuesta mediante el shell de administración de Lync Server

1.  Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

3.  Ejecute:
    
        Get-CsRgsAgentGroup

4.  Compruebe que todos los grupos de agentes del entorno de Lync Server 2010 están incluidos en la lista.

5.  Ejecute:
    
        Get-CsRgsQueue

6.  Compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.

7.  Ejecute:
    
        Get-CsRgsWorkflow

8.  Compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 están incluidos en la lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

