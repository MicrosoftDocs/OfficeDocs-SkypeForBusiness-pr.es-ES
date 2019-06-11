---
title: 'Lync Server 2013: Configurar el DNS para el equilibrio de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurar el DNS para el equilibrio de carga en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o en miembro del grupo DnsAdmins.

El equilibrio de carga del sistema de nombres de dominio (DNS) equilibra el tráfico de red que es exclusivo de Lync Server 2013, como el tráfico SIP y el tráfico de medios. El equilibrio de carga de DNS es compatible con los grupos de aplicaciones front-end, los conjuntos de extremos, los grupos de directores y los conjuntos de mediación independiente. Un grupo configurado para usar el equilibrio de carga de DNS debe tener dos nombres de dominio completos (FQDN) definidos: el FQDN de la agrupación normal que usa el equilibrio de carga de DNS (por ejemplo, pool1.contoso.com) y que se resuelve en la IP física de los servidores del grupo y otro FQDN para los servicios web del grupo (por ejemplo, web1.contoso.net), que se resuelve en la dirección IP virtual del grupo. Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.

<div>


> [!NOTE]  
> El equilibrio de carga de hardware sigue siendo necesario para el tráfico HTTPS del cliente al servidor.



</div>

Para poder usar el equilibrio de carga de DNS, debe hacer lo siguiente:

1.  Invalide el FQDN del grupo de servicios Web interno.
    
    <div>
    

    > [!WARNING]  
    > Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

2.  Cree registros de host DNS para resolver el FQDN del grupo a las direcciones IP de todos los servidores del grupo.

3.  Habilite la aleatoriedad de la dirección IP o, para DNS de Windows Server, habilite la operación por turnos.
    
    <div>
    

    > [!NOTE]  
    > La operación por turnos debe estar habilitada de forma predeterminada.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Para invalidar el FQDN de los servicios Web internos

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de la consola, expanda el nodo agrupaciones front-end de Enterprise Edition.

3.  Haga clic con el botón secundario en el grupo, haga clic en **Editar propiedades**y, a continuación, en **servicios web**.

4.  Debajo de **servicios Web internos**, seleccione la casilla invalidar **FQDN** .

5.  Escriba el FQDN del grupo de servidores que se resuelve en las direcciones IP físicas de los servidores del grupo.

6.  Debajo de **servicios web externos**, escriba el FQDN del grupo externo que se resuelve en las direcciones IP virtuales del grupo y, a continuación, haga clic en **Aceptar**.

7.  En el árbol de consola, haga clic en **Lync Server 2013**y, a continuación, en el panel **acciones** , haga clic en **publicar topología**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Para crear registros de host DNS (A) para todos los servidores de grupo internos

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **DNS**.

2.  En el **Administrador de DNS**, haga clic en el servidor DNS que administra los registros para expandirlo.

3.  Haga clic en **zonas de búsqueda directa** para expandirlo.

4.  Haga clic con el botón secundario en el dominio DNS al que tiene que agregar registros y, a continuación, haga clic en **nuevo host (a o aaaa)**.

5.  En el cuadro **Nombre**, escriba el nombre del registro de host (el nombre de dominio se anexará automáticamente).

6.  En el cuadro Dirección IP, escriba la dirección IP del servidor frontal individual y, después, seleccione **crear registro de puntero (PTR) asociado** o **permitir que cualquier usuario autenticado actualice los registros DNS con el mismo nombre de propietario**, si procede.

7.  Siga creando registros para todos los servidores front-end de miembros que participarán en el equilibrio de carga de DNS.
    
    Por ejemplo, si tiene un grupo denominado pool1.contoso.com y tres servidores front-end, deberá crear las siguientes entradas DNS:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Tipo</th>
    <th>Datos</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obtener información detallada sobre la creación de registros de host DNS (A), vea [configurar registros de host DNS para Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Para habilitar la operación por turnos en Windows Server

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **DNS**.

2.  Expanda **DNS**, haga clic con el botón secundario en el servidor DNS que desea configurar y, después, haga clic en **propiedades**.

3.  Haga clic en la pestaña **avanzadas** , seleccione **Habilitar** ordenación por turnos y **Habilitar ordenación de máscaras de máscara**y, después, haga clic en **Aceptar**.
    
    ![Cuadro de diálogo Round Robin de DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Cuadro de diálogo Round Robin de DNS")

<div>


> [!NOTE]  
> Esta característica debe estar habilitada de forma predeterminada.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

