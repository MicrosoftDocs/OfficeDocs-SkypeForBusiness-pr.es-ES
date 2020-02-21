---
title: Migrar los grupos de respuesta
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
ms.openlocfilehash: 36b37fc6a67a1935c442edb4e2e8ef0d8812315c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar los grupos de respuesta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Una vez que los usuarios se han movido a grupos de servidores de Lync Server 2013, puede migrar los grupos de respuesta. Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo y archivos de audio, y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Lync Server 2013. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.

<div>


> [!NOTE]  
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar. En concreto, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.



</div>

Antes de migrar los grupos de respuesta, debe haber implementado un grupo de servidores de 2013 de Lync Server que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> Puede crear nuevos grupos de respuesta 2013 de Lync Server en el grupo de Lync Server 2013 antes de migrar los grupos de respuesta heredados.



</div>

Para migrar grupos de respuesta de un grupo heredado a la versión 2013 de Lync Server, ejecute el cmdlet **Move-CsRgsConfiguration** . Antes de ejecutar el **Move-CsRgsConfiguration**, primero debe instalar el paquete de interfaces de Compatibilidad con versiones anteriores del Instrumental de administración de Windows (WMI). Instale esta aplicación al ejecutar OCSWMIBC.msi. Puede encontrar el archivo OCSWMIBC.msi en los medios de instalación en la carpeta de instalación.

<div>


> [!IMPORTANT]  
> El cmdlet de migración del grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.



</div>

Después de migrar los grupos de respuesta, debe actualizar la URL que los agentes formales usan para iniciar y cerrar sesión en sus grupos de respuesta, y usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron siguiera.

<div>


> [!WARNING]  
> Al migrar grupos de respuesta, los grupos de respuesta de Office Communications Server 2007 R2 no se quitan. No quite los grupos de respuesta de Office Communications Server 2007 R2. Si quita un grupo de respuesta de Office Communications Server 2007 R2, los grupos de respuesta de Lync Server 2013 dejarán de funcionar.



</div>

<div>


> [!IMPORTANT]  
> Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores. También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración. Si se quita un grupo de respuesta de Office Communications Server 2007 R2, puede restaurar los grupos de respuesta a partir de la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 que se ejecuten de nuevo.



</div>

Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.

<div>


> [!IMPORTANT]  
> Se recomienda no eliminar ningún dato los grupos de respuesta del grupo de servidores heredado hasta retirar dicho grupo de servidores.



</div>

El procedimiento que se describe a continuación para migrar configuraciones de grupo de respuesta supone que tiene una relación de uno a uno entre los grupos de servidores heredados y los grupos de servidores de 2013 de Lync Server. Si tiene previsto consolidar o dividir grupos durante la migración y la implementación, debe planear el grupo de servidores heredado asignado a cada grupo de servidores de Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar configuraciones de grupo de respuesta

1.  Busque OCSWMIBC.msi en la carpeta de instalación de los medios de instalación e instálelo.

2.  Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.

3.  Abra el Shell de administración de Lync Server.

4.  Escriba lo siguiente en la línea de comandos:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por ejemplo:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si ha implementado la pestaña grupo de respuesta para Microsoft Office Communicator 2007 R2 en su entorno de Office Communications Server 2007 R2, quite la pestaña del archivo Tabs. XML de Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Los agentes formales utilizaban la pestaña Grupo de respuesta para iniciar sesión en sus grupos de respuesta para así poder recibir llamadas. Si ha implementado la pestaña grupo de respuesta, eligió la ubicación del archivo Tabs. XML de Office Communicator 2007 R2 cuando lo implementó.

    
    </div>

6.  Proporcione a los usuarios la dirección URL actualizada que los agentes necesitan para iniciar y cerrar sesión en sus grupos de respuesta.
    
    <div>
    

    > [!NOTE]  
    > La dirección URL suele https://webpoolFQDN/RgsClients/Tab.aspxser, donde fqdngrupoweb es el nombre de dominio completo (FQDN) del grupo de servidores web que está asociado al grupo de servidores que acaba de migrar a Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Este paso no es necesario después de que los usuarios actualicen a Lync 2013 porque la dirección URL está disponible en el menú <STRONG>herramientas</STRONG> de Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para comprobar la migración del grupo de respuesta mediante el panel de control de Lync Server

1.  Abra el Panel de control de Lync Server.

2.  En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.

3.  En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se incluyen en la lista.

4.  Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

5.  Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se incluyen en la lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Para comprobar la migración del grupo de respuesta mediante cmdlets

1.  Abra el Shell de administración de Lync Server.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed

2.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsRgsAgentGroup

3.  Compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se incluyen en la lista.

4.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsRgsQueue

5.  Compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

6.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsRgsWorkflow

7.  Compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se incluyen en la lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

