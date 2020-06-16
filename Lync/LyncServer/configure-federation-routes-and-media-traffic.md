---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5e9b7ad3f08d9ebf129c478bbcf94bed7845ef1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto de Lync Server 2013, debe realizar la transición de la ruta de Federación de sus servidores perimetrales de Lync Server 2010 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.

Use los siguientes procedimientos para realizar la transición de la ruta de Federación y la ruta de tráfico de medios del servidor perimetral y el director de Lync Server 2010 a su servidor perimetral de Lync Server 2013 para una implementación en un solo sitio.

<div>


> [!IMPORTANT]  
> Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Lync Server 2013 y Lync Server 2010. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.



</div>

<div>


> [!IMPORTANT]  
> Si el servidor perimetral de Lync Server 2010 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Lync Server 2010 a Lync Server 2013 y, después, retirar el servidor perimetral de Lync Server 2010 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Lync Server 2010 no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Lync Server 2013, se hayan configurado las directivas y los certificados XMPP, se haya configurado el socio federado de XMPP en Lync Server 2013 y se hayan actualizado las entradas DNS.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para quitar la asociación de federación heredada de los sitios de Lync Server 2013

1.  En el servidor front-end de Lync Server 2013, abra la topología existente en Topology Builder.

2.  En el panel izquierdo, desplácese al nodo del sitio, que se encuentra justo debajo de **Lync Server**.

3.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.

4.  En el panel izquierdo, seleccione **Ruta de federación**.

5.  En **asignación de ruta de Federación del sitio**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado de Lync Server 2010.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En **Topology Builder**, seleccione el nodo en primera posición **Lync Server**.

8.  En el menú **Acción**, haga clic en **Publicar topología**.

9.  Haga clic en **Siguiente** para completar el proceso de publicación y, después, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como servidor perimetral no federado

1.  En el panel izquierdo, desplácese al nodo **Lync Server 2010** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.

3.  Seleccione **General** en el panel izquierdo.

4.  Desactive la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página.
    
    ![Editar propiedades, general, desactive habilitar Federación](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propiedades, general, desactive habilitar Federación")

5.  En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

6.  Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

7.  Compruebe que está deshabilitada la federación en el servidor perimetral heredado.
    
    ![Generador de topologías, grupo de servidores perimetrales, Federación deshabilitada](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, Federación deshabilitada")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Para configurar certificados en el servidor perimetral de Lync Server 2010

1.  Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Lync Server 2010 heredado.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.

3.  Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  El certificado de interfaz interno del servidor perimetral de Lync Server 2013 debe solicitarse a una entidad de certificación de confianza y asignarse.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Para cambiar la ruta de federación de Lync Server 2010 y usar el servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.

3.  Seleccione **General** en el panel izquierdo.

4.  Active la entrada de la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, seleccione **Aceptar** para cerrar la página.
    
    ![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")

5.  En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

6.  Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

7.  Compruebe que **Federación (puerto 5061)** está **Habilitado**.
    
    ![Generador de topologías, grupo de servidores perimetrales, Federación habilitada](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, Federación habilitada")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Para actualizar al próximo salto de la federación del servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que se muestra y, a continuación, haga clic en **Editar propiedades**.

3.  En la página **General** , en **selección**de próximo salto, seleccione en la lista desplegable el grupo de servidores de Lync Server 2013.
    
    ![Cuadro de diálogo Editar propiedades, página de salto siguiente](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página de salto siguiente")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  En **generador de topologías**, seleccione el nodo superior **Lync Server** .

6.  En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013

1.  En el generador de topologías, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, a continuación, al grupo de servidores que se encuentra debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.
    
    ![Editar propiedades, general, asociar grupo de servidores perimetrales](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propiedades, general, asociar grupo de servidores perimetrales")

4.  En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para activar la federación del servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que se muestra y, a continuación, haga clic en **Editar propiedades**.
    
    <div>
    

    > [!NOTE]  
    > La Federación solo se puede habilitar para un único grupo de servidores perimetrales. Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.

    
    </div>

3.  En la página **General**, compruebe que está activada la opción de configuración **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
    ![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, navegue hasta el nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.

7.  En el panel izquierdo, haga clic en **Ruta de federación**.

8.  En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Lync Server 2013 que aparece en la lista.
    
    ![Editar propiedades, página Ruta de Federación](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propiedades, página Ruta de Federación")

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.
    
    Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios de configuración en el servidor perimetral

1.  En **generador de topologías**, seleccione el nodo superior **Lync Server** .

2.  En el menú **Acción**, seleccione **Publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    
    <div>
    

    > [!NOTE]  
    > Es posible que aparezca el mensaje siguiente:<BR><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión más reciente del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Lync Server y compruebe que, en el registro SRV de DNS externo, se enumeran todos los servidores perimetrales habilitados para federación.</STRONG><BR>Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar el servidor perimetral de Lync Server 2013

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.
    
    <div>
    

    > [!NOTE]  
    > If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.

    
    </div>

3.  A continuación, detenga el **servidor perimetral de acceso de Lync Server** en cada equipo servidor perimetral.

4.  Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.

5.  En la lista de servicios, busque **Servidor perimetral de acceso de Lync Server**.

6.  Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.

7.  Establezca el Tipo de inicio en **Deshabilitado**.

8.  Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

