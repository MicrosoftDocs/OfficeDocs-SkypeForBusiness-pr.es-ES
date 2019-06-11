---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842784"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

 


La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red. Después de migrar a su grupo piloto de Lync Server 2013, tendrá que realizar una transición de la ruta de Federación de los servidores perimetrales de Microsoft Office Communications Server 2007 R2 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.

Use los procedimientos que se describen a continuación para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral de Office Communications Server 2007 R2 y el director a su servidor perimetral de Lync Server 2013, para una implementación de un solo sitio.


> [!IMPORTANT]  
> Cambiar la ruta de Federación y la ruta del tráfico multimedia requiere que programe el tiempo de mantenimiento de los servidores perimetrales de Lync Server 2013 y de Office Communications Server 2007 R2. Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario. También debe proporcionar una notificación suficiente a los usuarios finales. Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización.




> [!IMPORTANT]  
> Si el servidor perimetral de Office Communications Server 2007 R2 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, los procedimientos de esta sección para realizar la transición de la configuración de Federación a un servidor de Lync 2013 servidor perimetral no es compatible. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Office Communications Server 2007 R2 a Lync Server 2013 y, después, retirar el servidor perimetral de Office Communications Server 2007 R2 antes de habilitar la Federación en Servidor perimetral 2013 de Lync Server. Para obtener más información, consulte los temas siguientes: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Mover los usuarios restantes a Lync Server 2013</A></P>
> <LI>
> <P>"Quitar los servidores y roles de servidor" en<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Office Communications Server 2007 R2 no podrán comunicarse con el socio de XMPP federado hasta que todos los usuarios hayan movido a Lync Server 2013, directivas XMPP y se han configurado certificados, el socio XMPP federado se ha configurado en Lync Server 2013 y, por último, se han actualizado las entradas DNS.



Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. También es posible delegar los derechos de usuario y permisos adecuados para agregar roles de servidor. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para quitar la Asociación de Federación heredada de sitios de 2013 de Lync Server

1.  Abra la topología de la agrupación piloto con el generador de topología.

2.  En el panel de la izquierda, vaya al nodo del sitio.

3.  Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.

4.  Seleccione **ruta de Federación** en el panel de la izquierda.

5.  En asignación de enrutamiento de Federación de sitios, desactive la casilla situada junto a **Habilitar la Federación SIP** para deshabilitar la ruta de Federación a través de la **BackCompatSite**.
    
    ![Editar propiedades, ruta de Federación] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Editar propiedades, ruta de Federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En el **generador**de topologías, seleccione el nodo de nivel superior de **Lync Server**.

8.  En el menú **acción** , haga clic en **publicar topología** y complete el asistente.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como servidor perimetral de no Federación

1.  Desde el **generador**de topologías, en el menú **acción** haga clic en **combinar topología de Office Communications Server 2007 R2**.

2.  Haga clic en **Siguiente** para continuar.

3.  En la **configuración de especificar Edge**, seleccione el **FQDN interno del servidor perimetral** que está configurado actualmente para la Federación y, a continuación, haga clic en **cambiar**.
    
    ![Combinar OCS 2007 R2 Topology, especificar configuración perimetral] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Combinar OCS 2007 R2 Topology, especificar configuración perimetral")

4.  Haga clic en **siguiente** y acepte la configuración predeterminada hasta llegar a la página **especificar borde externo** :
    
    El ![generador de topología especifica la página de borde externo] El (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "generador de topología especifica la página de borde externo")

5.  En **especificar borde externo**, desactive la casilla **este grupo perimetral se usa para la Federación y la conectividad de mensajería instantánea pública** . Esto quitará la Asociación de Federación con el BackCompatSite.
    

    > [!IMPORTANT]  
    > Este paso es importante. Debe desactivar esta opción para quitar la Asociación de Federación heredada.



6.  Haga clic en **siguiente** y acepte la configuración predeterminada de las páginas restantes del asistente.

7.  En **Resumen**, haga clic en **siguiente** para empezar a combinar las topologías.

8.  En la columna **Estado** , compruebe que el valor es **correcto**y, a continuación, haga clic en **Finalizar** para cerrar el asistente.

9.  En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.

10. Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.
    
    ![Generador de topología con sitio que se muestra después de la combinación] (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generador de topología con sitio que se muestra después de la combinación")
    
    Tal como se muestra en la ilustración anterior, la **Federación SIP** , ubicada en asignación de la **ruta de Federación de sitios** , se establece en deshabilitado. ****

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Para configurar certificados en el servidor perimetral de Lync Server 2013

1.  Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Office Communications Server 2007 R2 heredado.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del proxy de acceso del paso anterior.

3.  Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  El certificado de interfaz interno del servidor perimetral de Lync Server 2013 no debe cambiarse.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Para cambiar la ruta de Federación de Office Communications Server 2007 R2 para usar Lync Server 2013 Edge Server

1.  En el servidor de Office Communications Server 2007 R2 Standard Edition o el servidor front-end, abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el panel izquierdo, expanda el nodo superior y, a continuación, haga clic con el botón derecho en el nodo del **bosque** . Seleccione **propiedades**y, a continuación, haga clic en **propiedades globales**.

3.  Haga clic en la pestaña **Federación** .

4.  Active la casilla para habilitar la Federación y la conectividad de mensajería instantánea pública.

5.  Escriba el FQDN del servidor perimetral de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    ![Propiedades globales de OCS, ficha Federación] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propiedades globales de OCS, ficha Federación")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para activar la Federación de Lync Server 2013 Edge Server

1.  Desde el generador de topologías, en el panel izquierdo, vaya al nodo de **** las agrupaciones perimetrales de Lync Server 2013.

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.
    

    > [!NOTE]  
    > La Federación solo se puede habilitar para un único grupo de borde. Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación.



3.  En la página **General** , active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .
    
    ![Editar propiedades, general, habilitar Federación perimetral] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propiedades, general, habilitar Federación perimetral")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, vaya al nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.

7.  En el panel de la izquierda, haga clic en **ruta de Federación**.

8.  En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, en la lista, seleccione el servidor perimetral 2013 de Lync Server en la lista.

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .
    
    ![Editar propiedades, general, asociar grupo Edge] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propiedades, general, asociar grupo Edge")
    
    Para implementaciones de varios sitios, complete este procedimiento en cada sitio.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar la ruta multimedia de salida de Lync Server 2013 Edge Server

1.  Desde el **generador**de topologías, vaya al grupo de servidores de Lync Server 2013, debajo de **los servidores de aplicaciones para** el usuario de la edición Standard o **Enterprise Edition**.

2.  Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

3.  En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** .

4.  En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.
    
    ![Cuadro de diálogo Editar propiedades, asociar grupo perimetral] (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Cuadro de diálogo Editar propiedades, asociar grupo perimetral")

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios en la configuración del servidor perimetral

1.  En el **generador**de topologías, seleccione el nodo de nivel superior de **Lync Server**.

2.  En el menú **acción** , seleccione **publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.
    

    > [!NOTE]  
    > Es posible que vea el siguiente mensaje:<BR><STRONG>ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Office Communications Server 2007 R2 o Lync Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.</STRONG><BR>Esta advertencia es esperada y puede ignorarse de forma segura.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Para comprobar la Federación y el acceso remoto para usuarios externos

1.  En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.

2.  Para comprobar el estado de la Federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:
    
        Get-CsAccessEdgeConfiguration

3.  Para habilitar la Federación y el acceso remoto, en la línea de comandos, escriba lo siguiente:
    
        Set-CsAccessEdgeConfiguration
    
    Para obtener más información sobre estos cmdlets, vea los siguientes temas: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) y [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  Espere hasta que se haya completado la replicación antes de conectar los servidores perimetrales de Lync Server 2013 y pruebe la Federación y el acceso externo.

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar el servidor perimetral 2013 de Lync Server

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.
    

    > [!NOTE]  
    > Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro A de DNS para que la Federación resuelva el nuevo servidor perimetral de acceso de Lync Server. Para lograr esto con el mínimo de interrupciones, reduzca el valor de TTL para el FQDN de perimetral de acceso de Lync Server externo de modo que, cuando se actualice DNS para que apunte al nuevo servidor perimetral de acceso de Lync Server, la Federación y el acceso remoto se actualizarán rápidamente.



3.  Después, detenga la aplicación **perimetral de acceso de Lync Server** desde cada equipo servidor perimetral.

4.  Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.

5.  En la lista servicios, busque **Office Communications Server Access Edge**.

6.  Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio.

7.  Establezca el tipo de inicio **** en deshabilitado.

8.  Haga clic en **Aceptar** para cerrar la ventana **propiedades** .

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Para probar la conectividad de usuarios externos y acceso externo

  - Usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.

  - Los usuarios de cada proveedor de servicios de mensajería instantánea pública que su organización admita (y para el que se haya completado el aprovisionamiento) se comuniquen con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.

  - Comprobar que los usuarios anónimos pueden unirse a conferencias.

  - Un usuario alojado en Office Communications Server 2007 R2 con acceso de usuario remoto (que inicia sesión en Office Communications Server 2007 R2 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.

  - Un usuario hospedado en Lync Server 2013 con acceso de usuario remoto (iniciar sesión en Lync Server 2013 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.

