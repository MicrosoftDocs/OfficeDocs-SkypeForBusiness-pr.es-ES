---
title: 'Lync Server 2013: Configurar el DNS para el equilibrio de carga'
TOCTitle: Configurar el DNS para el equilibrio de carga
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48274589
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el DNS para el equilibrio de carga en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

El equilibrio de carga del Sistema de nombres de dominio (DNS) equilibra el tráfico de red exclusivo de Lync Server 2013, como el tráfico SIP y el tráfico de medios. El equilibrio de carga de DNS es compatible con los grupos de servidores front-end, los grupos de servidores perimetrales, los grupos de directores y los grupos de servidores de mediación independientes. Un grupo configurado para usar el equilibrio de carga de DNS debe tener definidos dos nombres de dominio completos (FQDN): un FQDN de grupo que se use habitualmente en el equilibrio de carga de DNS (por ejemplo, pool1.contoso.com) y que se resuelva en las IP físicas de los servidores del grupo, y otro para el Servicios web del grupo (por ejemplo, web1.contoso.net) y que se resuelva en la dirección IP virtual del grupo. Para obtener información detallada sobre el equilibrio de carga de DNS, consulte [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.


> [!NOTE]
> Sigue necesitando usar equilibro de carga de hardware para el tráfico HTTPS de cliente a servidor.



Antes de usar el equilibrio de carga de DNS, deberá hacer lo siguiente:

1.  Invalidar el FQDN de grupo del Servicios web interno.
    
    > [!WARNING]  
    > Si decide reemplazar los servicios web internos con un FQDN definido por usted mismo, cada FQDN debe ser único en cualquier Grupo de servidores front-end, Director o Grupo de directores.
    


2.  Crear registros de host A de DNS con los que el FQDN del grupo se resuelva en las direcciones IP de todos los servidores del grupo.

3.  Habilitar la selección aleatoria de direcciones IP o, en el caso de un DNS de Windows Server, habilitar la característica de round robin.
    

    > [!NOTE]
    > Debe habilitarse el Round robin de manera predeterminada.



## Para invalidar el FQDN de los servicios web internos

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de la consola, expanda el nodo de grupos de servidores front-end Enterprise Edition.

3.  Haga clic con el botón secundario en el grupo, haga clic en **Editar propiedades** y, a continuación, haga clic en **Servicios web**.

4.  En **Servicios web internos**, active la casilla **Invalidar nombre de dominio completo**.

5.  Escriba el FQDN de grupo que se resuelva en las direcciones IP físicas de los servidores de dicho grupo.

6.  En **Servicios web externos**, escriba el FQDN de grupo externo que se resuelva en las direcciones IP virtuales del grupo y haga clic en **Aceptar**.

7.  En el árbol de la consola, haga clic en **Lync Server 2013**y, a continuación, en el panel **Acciones**, haga clic en **Publicar topología**.

## Para crear registros de host (A) DNS para todos los servidores de grupo internos

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y, finalmente, **DNS**.

2.  En el **Administrador de DNS**, haga clic en el servidor DNS que administra los registros para expandirlo.

3.  Haga clic en **Zonas de búsqueda directa** para expandirlo.

4.  Haga clic con el botón secundario en el dominio DNS al que necesita agregar registros y haga clic en **Host nuevo (A o AAAA)**.

5.  En el cuadro **Nombre**, escriba el nombre del registro de host (el nombre de dominio se anexará automáticamente).

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
    
    Para obtener información detallada sobre cómo crear registros de host (A) DNS, consulte [Configurar registros de host DNS para Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

## Para habilitar el round robin en Windows Server

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y, finalmente, **DNS**.

2.  Expanda **DNS**, haga clic con el botón secundario en el servidor DNS que quiera configurar y, a continuación, haga clic en **Propiedades**.

3.  Haga clic en la pestaña **Opciones avanzadas**, seleccione **Habilitar la función Round Robin** y **Habilitar orden de máscara de red** y, a continuación, haga clic en **Aceptar**.
    
    ![Cuadro de diálogo Round Robin de DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Cuadro de diálogo Round Robin de DNS")


> [!NOTE]
> Esta característica debe habilitarse de manera predeterminada.



## Vea también

#### Conceptos

[Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md)

