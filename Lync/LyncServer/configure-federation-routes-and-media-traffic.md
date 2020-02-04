---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red. Después de migrar a su grupo piloto de Lync Server 2013, tendrá que realizar una transición de la ruta de Federación de sus servidores perimetrales de Lync Server 2010 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.

Use los procedimientos siguientes para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral de Lync Server 2010 y el director a su servidor perimetral de Lync Server 2013, para una implementación de un solo sitio.

<div>


> [!IMPORTANT]  
> Cambiar la ruta de Federación y la ruta del tráfico multimedia requiere que programe el tiempo de mantenimiento de los servidores perimetrales de Lync Server 2013 y Lync Server 2010. Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario. También debe proporcionar una notificación suficiente a los usuarios finales. Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización.



</div>

<div>


> [!IMPORTANT]  
> Si su servidor perimetral antiguo de Lync Server 2010 está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, no se admiten los procedimientos de esta sección. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Lync Server 2010 a Lync Server 2013 y, después, retirar el servidor perimetral de Lync Server 2010 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Lync Server 2010 no podrán comunicarse con el socio federado del XMPP hasta que todos los usuarios hayan pasado a Lync Server 2013, las directivas XMPP y los certificados se han configurado, el socio de XMPP federado se ha configurado en Lync Server 2013 y, por último, se han actualizado las entradas DNS.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para quitar la Asociación de Federación heredada de sitios de 2013 de Lync Server

1.  En el servidor front-end de Lync Server 2013, abra la topología existente en el generador de topologías.

2.  En el panel de la izquierda, vaya al nodo del sitio, que se encuentra directamente debajo de **Lync Server**.

3.  Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.

4.  En el panel de la izquierda, seleccione **ruta de Federación**.

5.  En **asignación de ruta de Federación de sitios**, desactive la casilla de verificación **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado de Lync Server 2010.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server**.

8.  En el menú **acción** , haga clic en **publicar topología**.

9.  Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como servidor perimetral de no Federación

1.  En el panel de la izquierda, vaya al nodo de **2010 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .

2.  Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.

3.  Seleccione **General** en el panel de la izquierda.

4.  Desactive la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y seleccione **Aceptar** para cerrar la página.
    
    ![Editar propiedades, general, habilitar la Federación](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propiedades, general, habilitar la Federación")

5.  En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.

6.  Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.

7.  Comprobar que la Federación del servidor perimetral heredado está deshabilitada.
    
    ![Generador de topología, grupo Edge, Federación deshabilitada](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generador de topología, grupo Edge, Federación deshabilitada")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Para configurar certificados en el servidor perimetral de Lync Server 2010

1.  Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Lync Server 2010.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del proxy de acceso del paso anterior.

3.  Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  Debe solicitarse el certificado de interfaz interno del servidor perimetral de Lync Server 2013 de una entidad de certificación de confianza y se asignará.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Para cambiar la ruta de Federación de Lync Server 2010 para usar Lync Server 2013 Edge Server

1.  Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .

2.  Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.

3.  Seleccione **General** en el panel de la izquierda.

4.  Seleccione la entrada de la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.
    
    ![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")

5.  En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.

6.  Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.

7.  Comprobar la **Federación (el puerto 5061)** está **habilitado**.
    
    ![Generador de topología, grupo Edge, Federación habilitada](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generador de topología, grupo Edge, Federación habilitada")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Para actualizar el próximo salto de la Federación de Lync Server 2013 Edge Server

1.  Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.

3.  En la página **General** , en **selección del próximo salto**, seleccione de la lista desplegable el grupo de servidores de Lync 2013.
    
    ![Cuadro de diálogo Editar propiedades, página de salto siguiente](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página de salto siguiente")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server** .

6.  En el menú **acción** , haga clic en **publicar topología** y complete el asistente.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar la ruta multimedia de salida de Lync Server 2013 Edge Server

1.  Desde el generador de topología, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, a los grupos de servidores de aplicaciones de usuario de la parte inferior **Standard Edition** o a los **grupos front-end de Enterprise Edition**.

2.  Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

3.  En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** .
    
    ![Editar propiedades, general, asociar grupo Edge](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propiedades, general, asociar grupo Edge")

4.  En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para activar la Federación de Lync Server 2013 Edge Server

1.  Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.
    
    <div>
    

    > [!NOTE]  
    > La Federación solo se puede habilitar para un único grupo de borde. Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación.

    
    </div>

3.  En la página **General** , compruebe que la opción **Habilitar Federación para este grupo perimetral (puerto 5061)** esté activada.
    
    ![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, vaya al nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.

7.  En el panel de la izquierda, haga clic en **ruta de Federación**.

8.  En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, en la lista, seleccione el servidor perimetral 2013 de Lync Server en la lista.
    
    ![Editar propiedades, página de ruta de Federación](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propiedades, página de ruta de Federación")

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .
    
    Para implementaciones de varios sitios, complete este procedimiento en cada sitio.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios en la configuración del servidor perimetral

1.  En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server** .

2.  En el menú **acción** , seleccione **publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.
    
    <div>
    

    > [!NOTE]  
    > Es posible que vea el siguiente mensaje:<BR><STRONG>ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Lync Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.</STRONG><BR>Esta advertencia es esperada y puede ignorarse de forma segura.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar el servidor perimetral 2013 de Lync Server

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.
    
    <div>
    

    > [!NOTE]  
    > Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Lync Server. Para lograr esto con el mínimo de interrupciones, reduzca el valor de TLL del FQDN del perímetro externo de acceso de Lync Server para que cuando se actualice DNS para que apunte al nuevo perimetral de acceso de Lync Server, la Federación y el acceso remoto se actualizarán rápidamente.

    
    </div>

3.  Después, detenga la aplicación **perimetral de acceso de Lync Server** desde cada equipo servidor perimetral.

4.  Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.

5.  En la lista servicios, busque **Lync Server Access Edge**.

6.  Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio.

7.  Establezca el tipo de inicio en **deshabilitado**.

8.  Haga clic en **Aceptar** para cerrar la ventana **propiedades** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

