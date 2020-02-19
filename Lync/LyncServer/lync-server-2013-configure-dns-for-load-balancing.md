---
title: 'Lync Server 2013: configurar el DNS para el equilibrio de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257bd8d1d4874bb2483c16c2216c4b76b178a881
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurar el DNS para el equilibrio de carga en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

El equilibrio de carga del sistema de nombres de dominio (DNS) equilibra el tráfico de red que es único en Lync Server 2013, como el tráfico SIP y el tráfico multimedia. El equilibrio de carga de DNS es compatible con los grupos de servidores front-end, los grupos de servidores perimetrales, los grupos de directores y los grupos de servidores de mediación independientes. Un grupo configurado para usar el equilibrio de carga de DNS debe tener definidos dos nombres de dominio completos (FQDN): el FQDN de grupo de servidores normal que usa el equilibrio de carga de DNS (por ejemplo, pool1.contoso.com) y que se resuelve en las IP físicas de los servidores del grupo. y otro FQDN para los servicios web del grupo de servidores (por ejemplo, web1.contoso.net), que se resuelve en la dirección IP virtual del grupo de servidores. Para obtener más información sobre el equilibrio de carga de DNS, vea [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación referente a la planeación.

<div>


> [!NOTE]  
> Sigue necesitando usar equilibro de carga de hardware para el tráfico HTTPS de cliente a servidor.



</div>

Antes de usar el equilibrio de carga de DNS, deberá hacer lo siguiente:

1.  Invalide el FQDN del grupo de servicios Web interno.
    
    <div>
    

    > [!WARNING]  
    > Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

2.  Crear registros de host A de DNS con los que el FQDN del grupo se resuelva en las direcciones IP de todos los servidores del grupo.

3.  Habilitar la selección aleatoria de direcciones IP o, en el caso de un DNS de Windows Server, habilitar la característica de round robin.
    
    <div>
    

    > [!NOTE]  
    > Debe habilitarse el Round robin de manera predeterminada.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Para invalidar el FQDN de los servicios web internos

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de la consola, expanda el nodo de grupos de servidores front-end Enterprise Edition.

3.  Haga clic con el botón secundario en el grupo, haga clic en **Editar propiedades** y, a continuación, haga clic en **Servicios web**.

4.  En **Servicios web internos**, active la casilla **Invalidar nombre de dominio completo**.

5.  Escriba el FQDN de grupo que se resuelva en las direcciones IP físicas de los servidores de dicho grupo.

6.  En **Servicios web externos**, escriba el FQDN de grupo externo que se resuelva en las direcciones IP virtuales del grupo y haga clic en **Aceptar**.

7.  En el árbol de la consola, haga clic en **Lync Server 2013**y, a continuación, en el panel **acciones** , haga clic en **publicar topología**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Para crear registros de host (A) DNS para todos los servidores de grupo internos

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y, finalmente, **DNS**.

2.  En el **Administrador de DNS**, haga clic en el servidor DNS que administra los registros para expandirlo.

3.  Haga clic en **Zonas de búsqueda directa** para expandirlo.

4.  Haga clic con el botón secundario en el dominio DNS al que necesita agregar registros y haga clic en **Host nuevo (A o AAAA)**.

5.  En el cuadro **nombre** , escriba el nombre del registro de host (el nombre de dominio se anexará automáticamente).

6.  En el cuadro Dirección IP, escriba la dirección IP del servidor front-end individual y seleccione **Crear registro del puntero (PTR) asociado** o **Permitir a cualquier usuario autenticado actualizar registros DNS con el mismo nombre de propietario**, si procede.

7.  Siga creando registros para todos los servidores front-end miembro que vayan a participar en el equilibrio de carga de DNS.
    
    Por ejemplo, si tiene un grupo denominado pool1.contoso.com y tres servidores front-end, será necesario crear las siguientes entradas de DNS:
    
    
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
    
    Para obtener información detallada acerca de la creación de registros de host DNS (A), consulte [configure DNS host Records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Para habilitar el round robin en Windows Server

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y, finalmente, **DNS**.

2.  Expanda **DNS**, haga clic con el botón secundario en el servidor DNS que quiera configurar y, a continuación, haga clic en **Propiedades**.

3.  Haga clic en la pestaña **Opciones avanzadas**, seleccione **Habilitar la función Round Robin** y **Habilitar orden de máscara de red** y, a continuación, haga clic en **Aceptar**.
    
    ![Cuadro de diálogo Round Robin de DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Cuadro de diálogo Round Robin de DNS")

<div>


> [!NOTE]  
> Esta característica debe habilitarse de manera predeterminada.



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

