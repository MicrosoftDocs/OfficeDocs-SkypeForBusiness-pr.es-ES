---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar grupos de respuesta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Una vez que los usuarios se mueven a los grupos de Lync Server 2013, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo y archivos de audio, y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Lync 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013. Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.

<div>


> [!NOTE]  
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar. En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.



</div>

Antes de migrar grupos de respuesta, debe haber implementado un grupo de 2013 de Lync Server que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Puede crear nuevos grupos de respuesta de Lync Server 2013 en el grupo de servidores de Lync 2013 antes de migrar los grupos de respuesta heredados.



</div>

Para migrar grupos de respuesta de un grupo heredado a Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration** . Antes de poder ejecutar **Move-CsRgsConfiguration**, primero debe instalar el paquete interfaces de compatibilidad con versiones anteriores del instrumental de administración de Windows (WMI). Instale esta aplicación ejecutando OCSWMIBC. msi. Puede encontrar OCSWMIBC. msi en los medios de instalación de la carpeta SETUP.

<div>


> [!IMPORTANT]  
> El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar.



</div>

Después de migrar los grupos de respuesta, debe actualizar la dirección URL que usan los agentes formales para iniciar y cerrar sesión en sus grupos de respuesta, y usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron correctamente.

<div>


> [!WARNING]  
> Al migrar grupos de respuesta, los grupos de respuesta de Office Communications Server 2007 R2 no se quitan. No quite los grupos de respuesta de Office Communications Server 2007 R2. Si quita un grupo de respuesta de Office Communications Server 2007 R2, los grupos de respuesta de Lync Server 2013 dejarán de funcionar.



</div>

<div>


> [!IMPORTANT]  
> Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo. Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración. Si se elimina un grupo de respuesta de Office Communications Server 2007 R2, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 que se ejecutan de nuevo.



</div>

Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación. Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado.

<div>


> [!IMPORTANT]  
> Le recomendamos que no elimine ningún dato del grupo de respuesta del grupo heredado hasta que se desbloquee el grupo.



</div>

El procedimiento siguiente para migrar las configuraciones de grupos de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2013 de Lync Server. Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar las configuraciones de grupos de respuesta

1.  Busque OCSWMIBC. msi en la carpeta SETUP del disco de instalación e instálelo.

2.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

3.  Abra el shell de administración de Lync Server.

4.  En la línea de comandos, escriba:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si ha implementado la pestaña grupo de respuesta para Microsoft Office Communicator 2007 R2 en el entorno de Office Communications Server 2007 R2, quite la pestaña del archivo Tabs. XML de Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Agentes formales usó la ficha grupo de respuesta para iniciar sesión en sus grupos de respuesta antes de que puedan recibir llamadas. Si ha implementado la pestaña grupo de respuesta, eligió la ubicación del archivo Tabs. XML de Office Communicator 2007 R2 al implementarlo.

    
    </div>

6.  Proporcionar a los usuarios la dirección URL actualizada para que los agentes tengan que iniciar y cerrar sesión en sus grupos de respuesta.
    
    <div>
    

    > [!NOTE]  
    > La dirección URL es https://webpoolFQDN/RgsClients/Tab.aspxnormalmente, donde webpoolFQDN es el nombre de dominio completo (FQDN) del grupo de servidores web que está asociado al grupo que acaba de migrar a Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Este paso no es necesario después de que los usuarios actualicen a Lync 2013 porque la dirección URL está disponible en el menú <STRONG>herramientas</STRONG> de Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para comprobar la migración de grupos de respuesta mediante el panel de control de Lync Server

1.  Abra el panel de control de Lync Server.

2.  En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.

3.  En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 están incluidos en la lista.

4.  Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

5.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 están incluidos en la lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Para comprobar la migración de grupos de respuesta mediante cmdlets

1.  Abra el shell de administración de Lync Server.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

2.  En la línea de comandos, escriba:
    
        Get-CsRgsAgentGroup

3.  Compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 están incluidos en la lista.

4.  En la línea de comandos, escriba:
    
        Get-CsRgsQueue

5.  Compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

6.  En la línea de comandos, escriba:
    
        Get-CsRgsWorkflow

7.  Compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 están incluidos en la lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

