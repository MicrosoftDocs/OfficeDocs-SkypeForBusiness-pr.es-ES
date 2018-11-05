---
title: Configurar rutas de federación y tráfico multimedia
TOCTitle: Configurar rutas de federación y tráfico multimedia
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49889801
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar rutas de federación y tráfico multimedia

 

_**Última modificación del tema:** 2016-12-08_

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Tras migrar al grupo de servidores piloto de Lync Server 2013, debe realizar la transición de la ruta de federación de los servidores perimetrales de Microsoft Office Communications Server 2007 R2 a la ruta de federación de los servidores perimetrales de Lync Server 2013.

Utilice los procedimientos que se describen a continuación para realizar la transición de la ruta de federación y la ruta de tráfico de medios del servidor perimetral y el director de Office Communications Server 2007 R2 al servidor perimetral de Lync Server 2013, para una implementación en un único sitio.

> [!IMPORTANT]  
> Para cambiar la ruta de federación y la ruta de tráfico de medios, debe programar el tiempo de inactividad por mantenimiento para los servidores perimetrales de Lync Server 2013 y Office Communications Server 2007 R2. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.



> [!IMPORTANT]  
> > Si el servidor perimetral heredado de Office Communications Server 2007 R2 se configuró para utilizar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección para realizar la transición de la configuración de federación a un servidor perimetral de Lync Server 2013. Si los servicios perimetrales heredados se configuraron para utilizar el mismo FQDN, primero debe migrar todos los usuarios de Office Communications Server 2007 R2 a Lync Server 2013 y, posteriormente, retirar el servidor perimetral de Office Communications Server 2007 R2 antes de habilitar la federación en el servidor perimetral de Lync Server 2013. Para obtener más información, consulte los temas siguientes:
> <ul>
> <li><p><a href="move-remaining-users-to-lync-server-2013_1.md">Mover el resto de usuarios a Lync Server 2013</a></p></li>
> <li><p>&quot;Quitar servidores y roles de servidor&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268790%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268790&amp;clcid=0xC0A</a></p></li>
> </ul>


> [!IMPORTANT]  
> Si su federación XMPP se enruta mediante un servidor perimetral de Lync Server 2013, los usuarios del Office Communications Server 2007 R2 heredado no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se hayan trasladado a Lync Server 2013, se hayan configurado los certificados y las directivas de XMPP, se haya configurado el socio federado XMPP en Lync Server 2013 y, por último, se hayan actualizado las entradas de DNS.



Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y Admins. del dominio. También es posible delegar los derechos y permisos de usuario apropiados para agregar roles de servidor. Para obtener más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación referente a la implementación del servidor Standard Edition o del servidor Enterprise Edition. Para otros cambios de configuración, únicamente se necesita ser miembro del grupo RTCUniversalServerAdmins.

## Para quitar la asociación de federación heredada de los sitios de Lync Server 2013

1.  Abra la topología del grupo piloto en Generador de topologías.

2.  En el panel izquierdo, vaya al nodo del sitio.

3.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades** .

4.  Seleccione **Ruta de federación** en el panel izquierdo.

5.  En Asignación de ruta de federación del sitio, desactive la casilla de verificación situada junto a **Habilitar federación SIP** para deshabilitar la ruta de federación mediante **BackCompatSite**.
    
    ![Cuadro de diálogo Editar propiedades, ruta de federación](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Cuadro de diálogo Editar propiedades, ruta de federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En **Generador de topologías**, seleccione el nodo en primera posición **Lync Server**.

8.  En el menú **Acción** , haga clic en **Publicar topología** y complete el asistente.

## Para configurar el servidor perimetral heredado como servidor perimetral no federado

1.  En **Generador de topologías** , en el menú **Acción** , haga clic en **Combinar la topología de Office Communications Server 2007 R2** .

2.  Haga clic en **Siguiente** para continuar.

3.  En **Especificar configuración perimetral** , seleccione el **FQDN interno del servidor perimetral** que actualmente está configurado para la federación y, a continuación, haga clic en **Cambiar** .
    
    ![Combinar la topología OCS 2007 R2, especificar la configuración perimetral](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Combinar la topología OCS 2007 R2, especificar la configuración perimetral")

4.  Haga clic en **Siguiente** y acepte los valores predeterminados hasta llegar a la página **Especificar perímetro externo** :
    
    ![Página Especificar perímetro externo del Generador de topologías](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Página Especificar perímetro externo del Generador de topologías")

5.  En **Especificar perímetro externo** , desactive la casilla **Este grupo de servidores perimetrales se usa para federación y conectividad de mensajería instantánea pública** . Se quitará la asociación de federación con BackCompatSite.
    
    > [!IMPORTANT]  
    > Este paso es importante. Debe desactivar esta opción para quitar la asociación de federación heredada.
    


6.  Haga clic en **Siguiente** y acepte los valores predeterminados de las demás páginas del asistente.

7.  En **Resumen** , haga clic en **Siguiente** para comenzar a combinar topologías.

8.  En la columna **Estado** , compruebe que el valor sea **Correcto** y, a continuación, haga clic en **Finalizar** para cerrar el asistente.

9.  En el menú **Acción** , seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente** .

10. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.
    
    ![Generador de topologías con un sitio después de la combinación](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generador de topologías con un sitio después de la combinación")
    
    Como se muestra en la figura anterior, la **federación SIP** ubicada en **Asignación de ruta de federación del sitio** está definida en **Deshabilitado**.

## Para configurar certificados en el servidor perimetral de Lync Server 2013

1.  Exporte el certificado externo del servidor proxy de acceso, con la clave privada, desde el servidor perimetral de Office Communications Server 2007 R2 heredado.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.

3.  Asigne el certificado externo del servidor proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  No se debe modificar el certificado de la interfaz interna del servidor perimetral de Lync Server 2013.

## Para cambiar la ruta de federación de Office Communications Server 2007 R2 para que use el servidor perimetral de Lync Server 2013

1.  En el Office Communications Server 2007 R2Servidor Standard Edition o Servidor front-end, abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el panel izquierdo, expanda el nodo en primera posición y, a continuación, haga clic con el botón secundario en el nodo **Bosque** . Seleccione **Propiedades** y haga clic en **Propiedades globales** .

3.  Haga clic en la pestaña **Federación** .

4.  Seleccione la casilla para habilitar la federación y la conectividad de mensajería instantánea pública.

5.  Escriba el FQDN del Lync Server 2013  Servidor perimetral y, a continuación, haga clic en **Aceptar** .
    
    ![Propiedades globales de OCS, ficha Federación](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propiedades globales de OCS, ficha Federación")

## Para activar la federación del servidor perimetral de Lync Server 2013

1.  En Generador de topologías, en el panel izquierdo, navegue hasta el nodo Lync Server 2013**Grupos de servidores perimetrales** .

2.  Expanda el nodo, haga clic con el botón secundario en el Servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades** .
    

    > [!NOTE]
    > La federación solo se puede habilitar para un Grupo de servidores perimetrales único. Si tiene varios grupos de servidores perimetrales, seleccione uno para usar como Grupo de servidores perimetrales federado.



3.  En la página **General** , seleccione la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** .
    
    ![Editar propiedades, General, habilitar federación de servidores perimetrales](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Editar propiedades, General, habilitar federación de servidores perimetrales")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, navegue hasta el nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades** .

7.  En el panel izquierdo, haga clic en **Ruta de federación**.

8.  En **Asignación de ruta de federación del sitio** , seleccione **Habilitar federación SIP** y, a continuación, seleccione en la lista el Lync Server 2013  Servidor perimetral que se muestra.

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.
    
    ![Editar propiedades, General, Asociar grupos de servidores perimetrales](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propiedades, General, Asociar grupos de servidores perimetrales")
    
    Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.

## Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013

1.  En **Generador de topologías** , navegue hasta el grupo de servidores de Lync Server 2013 debajo de **Servidores front-end Standard Edition** o **Grupos de servidores front-end Enterprise Edition**.

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.

4.  En el cuadro de la lista desplegable, seleccione el servidor perimetral de Lync Server 2013.
    
    ![Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales")

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

## Para publicar cambios de configuración en el servidor perimetral

1.  En **Generador de topologías** , seleccione el nodo en primera posición **Lync Server** .

2.  En el menú **Acción** , haga clic en **Publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    

    > [!NOTE]
    > Es posible que aparezca el mensaje siguiente:<BR><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión superior del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Office Communications Server 2007 R2 o Lync Server, y compruebe que en el registro SRV de DNS externo se enumeran todos los servidores perimetrales habilitados para federación.</STRONG><BR>Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.



## Para comprobar la federación y el acceso remoto de usuarios externos

1.  Desde el servidor front-end de Lync Server 2013, abra la Shell de administración de Lync Server.

2.  Para verificar el estado de federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:
    
        Get-CsAccessEdgeConfiguration

3.  Para habilitar la federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:
    
        Set-CsAccessEdgeConfiguration
    
    Para obtener más información sobre estos cmdlets, consulte los siguientes temas: [Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAccessEdgeConfiguration) y [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration).

4.  Espere hasta que se complete la replicación antes de conectar los servidores perimetrales de Lync Server 2013 y probar la federación y el acceso externo.

## Para configurar el servidor perimetral de Lync Server 2013

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de cargas del hardware con el fin de enviar tráfico SIP para acceso (por lo general, el puerto 443) y federación (por lo general, el puerto 5061) al  Lync Server 2013  Servidor perimetral, en lugar del Servidor perimetral heredado.
    

    > [!NOTE]
    > Si no tiene un equilibrador de cargas del hardware, tendrá que actualizar el registro A de DNS para que la federación resuelva el nuevo servidor perimetral de acceso Lync Server. Para realizar esta tarea con las mínimas molestias, reduzca el valor TTL del FQDN del servidor perimetral de acceso a Lync Server externo, de modo que cuando se actualice el DNS para apuntar al nuevo servidor perimetral de acceso a Lync Server, la federación y el acceso remoto se actualicen rápidamente.



3.  A continuación, detenga **Servidor perimetral de acceso a Lync Server** en cada equipo Servidor perimetral.

4.  En cada equipo con el Servidor perimetral heredado, abra el applet **Servicios** en **Herramientas administrativas** .

5.  En la lista de servicios, busque **Acceso perimetral de Office Communications Server** .

6.  Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.

7.  Establezca el Tipo de inicio en **Deshabilitado** .

8.  Haga clic en **Aceptar** para cerrar la ventana **Propiedades** .

## Para comprobar la conectividad de los usuarios externos y el acceso externo

  - Los usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario de Office Communications Server 2007 R2. Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea públicos que la organización admita (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario de Lync Server 2013 y un usuario de Office Communications Server 2007 R2.

  - Compruebe que los usuarios anónimos se puedan unir a las conferencias.

  - Un usuario hospedado en Office Communications Server 2007 R2 que usa el acceso de usuarios remotos (inicia sesión en Office Communications Server 2007 R2 desde fuera de la intranet, pero sin una VPN) con un usuario de Lync Server 2013 y un usuario de Office Communications Server 2007 R2. Pruebe las características de mensajería instantánea, presencia, A/V y uso compartido de escritorio.

  - Un usuario hospedado en Lync Server 2013 que usa el acceso de usuarios remotos (inicia sesión en Lync Server 2013 desde fuera de la intranet, pero sin una VPN) con un usuario de Lync Server 2013 y un usuario de Office Communications Server 2007 R2. Pruebe las características de mensajería instantánea, presencia, A/V y uso compartido de escritorio.

