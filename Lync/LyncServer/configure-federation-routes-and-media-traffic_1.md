---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754966"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

 


La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto de Lync Server 2013, debe realizar la transición de la ruta de Federación de los servidores perimetrales de Microsoft Office Communications Server 2007 R2 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.

Use los procedimientos que se describen a continuación para realizar la transición de la ruta de Federación y la ruta de tráfico de medios desde el servidor perimetral y el director de Office Communications Server 2007 R2 a su servidor perimetral de Lync Server 2013 para una implementación en un solo sitio.


> [!IMPORTANT]  
> Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Lync Server 2013 y Office Communications Server 2007 R2. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.




> [!IMPORTANT]  
> Si el servidor perimetral de Office Communications Server 2007 R2 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección para realizar la transición de la configuración de Federación a un servidor perimetral de Lync Server 2013. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Office Communications Server 2007 R2 a Lync Server 2013 y, a continuación, retirar el servidor perimetral de Office Communications Server 2007 R2 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013. Para obtener más información, consulte los temas siguientes: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Mover los usuarios restantes a Lync Server 2013</A></P>
> <LI>
> <P>"Quitar servidores y roles de servidor" en<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Office Communications Server 2007 R2 no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Lync Server 2013, se hayan configurado las directivas y los certificados XMPP, se haya configurado el socio federado de XMPP en Lync Server 2013 y se hayan actualizado las entradas DNS.



Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins. También es posible delegar los derechos de usuario y los permisos adecuados para agregar roles de servidor. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para quitar la asociación de federación heredada de los sitios de Lync Server 2013

1.  Abra la topología del grupo piloto en Generador de topologías.

2.  En el panel izquierdo, vaya al nodo del sitio.

3.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.

4.  Seleccione **Ruta de federación** en el panel izquierdo.

5.  En Asignación de ruta de federación del sitio, desactive la casilla de verificación situada junto a **Habilitar federación SIP** para deshabilitar la ruta de federación mediante **BackCompatSite**.
    
    ![Cuadro de diálogo Editar propiedades, ruta de Federación](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Cuadro de diálogo Editar propiedades, ruta de Federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En **Topology Builder**, seleccione el nodo en primera posición **Lync Server**.

8.  En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como servidor perimetral no federado

1.  En **Generador de topologías**, en el menú **Acción**, haga clic en **Combinar la topología de Office Communications Server 2007 R2**.

2.  Haga clic en **Siguiente ** para continuar.

3.  En **Especificar configuración perimetral**, seleccione el **FQDN interno del servidor perimetral** que actualmente está configurado para la federación y, a continuación, haga clic en **Cambiar**.
    
    ![Fusionar la topología de OCS 2007 R2, especificar la configuración perimetral](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionar la topología de OCS 2007 R2, especificar la configuración perimetral")

4.  Haga clic en **Siguiente** y acepte los valores predeterminados hasta llegar a la página **Especificar perímetro externo**:
    
    ![Página especificar borde externo en el generador de topologías](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Página especificar borde externo en el generador de topologías")

5.  En **Especificar perímetro externo**, desactive la casilla **Este grupo de servidores perimetrales se usa para federación y conectividad de mensajería instantánea pública**. Se quitará la asociación de federación con BackCompatSite.
    

    > [!IMPORTANT]  
    > Este paso es importante. Debe desactivar esta opción para quitar la asociación de federación heredada.



6.  Haga clic en **Siguiente** y acepte los valores predeterminados de las demás páginas del asistente.

7.  En **Resumen**, haga clic en **Siguiente** para comenzar a combinar las topologías.

8.  En la columna **Estado** , compruebe que el valor sea **correcto**y, a continuación, haga clic en **Finalizar** para cerrar el asistente.

9.  En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

10. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.
    
    ![Generador de topologías con sitio mostrado después de la combinación](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generador de topologías con sitio mostrado después de la combinación")
    
    Como se muestra en la figura anterior, la **federación SIP** ubicada en **Asignación de ruta de federación del sitio** está definida en **Deshabilitado**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Para configurar certificados en el servidor perimetral de Lync Server 2013

1.  Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Office Communications Server 2007 R2 heredado.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.

3.  Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  El certificado de interfaz interno del servidor perimetral de Lync Server 2013 no debe cambiarse.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Para cambiar la ruta de federación de Office Communications Server 2007 R2 para que use el servidor perimetral de Lync Server 2013

1.  En el servidor de Office Communications Server 2007 R2 Standard Edition o el servidor front-end, abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el panel izquierdo, expanda el nodo en primera posición y, a continuación, haga clic con el botón secundario en el nodo **Bosque**. Seleccione **Propiedades** y haga clic en **Propiedades globales**.

3.  Haga clic en la pestaña **Federación**.

4.  Seleccione la casilla para habilitar la federación y la conectividad de mensajería instantánea pública.

5.  Escriba el FQDN del servidor perimetral de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    ![Propiedades globales de OCS, ficha Federación](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propiedades globales de OCS, ficha Federación")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para activar la federación del servidor perimetral de Lync Server 2013

1.  En generador de topologías, en el panel izquierdo, vaya al nodo grupos de servidores **perimetrales** de Lync Server 2013.

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.
    

    > [!NOTE]  
    > La Federación solo se puede habilitar para un único grupo de servidores perimetrales. Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.



3.  En la página **General**, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
    ![Editar propiedades, general, habilitar Federación perimetral](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propiedades, general, habilitar Federación perimetral")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, navegue hasta el nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.

7.  En el panel izquierdo, haga clic en **Ruta de federación**.

8.  En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Lync Server 2013 que aparece en la lista.

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.
    
    ![Editar propiedades, general, asociar grupo de servidores perimetrales](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propiedades, general, asociar grupo de servidores perimetrales")
    
    Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013

1.  En el **generador de topologías**, navegue hasta el grupo de servidores de Lync Server 2013 debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.

4.  En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.
    
    ![Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales")

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios de configuración en el servidor perimetral

1.  En **Generador de topologías**, seleccione el nodo en primera posición **Lync Server**.

2.  En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    

    > [!NOTE]  
    > Es posible que aparezca el mensaje siguiente:<BR><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión superior del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Office Communications Server 2007 R2 o Lync Server, y compruebe que en el registro SRV de DNS externo se enumeran todos los servidores perimetrales habilitados para federación.</STRONG><BR>Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Para comprobar la federación y el acceso remoto de usuarios externos

1.  En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.

2.  Para verificar el estado de federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:
    
        Get-CsAccessEdgeConfiguration

3.  Para habilitar la federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:
    
        Set-CsAccessEdgeConfiguration
    
    Para obtener más información sobre estos cmdlets, consulte los siguientes temas: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) y [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).

4.  Espere hasta que se haya completado la replicación antes de poner en línea los servidores perimetrales de Lync Server 2013 y pruebe la Federación y el acceso externo.

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar el servidor perimetral de Lync Server 2013

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.
    

    > [!NOTE]  
    > Si no tiene un equilibrador de cargas del hardware, tendrá que actualizar el registro A de DNS para que la federación resuelva el nuevo servidor perimetral de acceso Lync Server. Para realizar esta tarea con las mínimas molestias, reduzca el valor TTL del FQDN del servidor perimetral de acceso a Lync Server externo, de modo que cuando se actualice el DNS para apuntar al nuevo servidor perimetral de acceso a Lync Server, la federación y el acceso remoto se actualicen rápidamente.



3.  A continuación, detenga el **servidor perimetral de acceso de Lync Server** en cada equipo servidor perimetral.

4.  Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.

5.  En la lista de servicios, busque **Servidor perimetral de acceso del servidor de Office Communications**.

6.  Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.

7.  Establezca el Tipo de inicio en **Deshabilitado**.

8.  Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Para comprobar la conectividad de los usuarios externos y el acceso externo

  - Usuarios de al menos un dominio federado, un usuario interno en Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.

  - Compruebe que los usuarios anónimos se pueden unir a las conferencias.

  - Un usuario hospedado en Office Communications Server 2007 R2 con acceso de usuarios remotos (inicio de sesión en Office Communications Server 2007 R2 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.

  - Un usuario hospedado en Lync Server 2013 con acceso de usuarios remotos (iniciando sesión en Lync Server 2013 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.

