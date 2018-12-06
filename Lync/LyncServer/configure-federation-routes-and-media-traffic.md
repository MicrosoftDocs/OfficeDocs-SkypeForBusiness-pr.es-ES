---
title: Configurar las rutas de federación y el tráfico multimedia
TOCTitle: Configurar las rutas de federación y el tráfico multimedia
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49889364
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las rutas de federación y el tráfico multimedia

 

_**Última modificación del tema:** 2012-10-15_

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Tras migrar al grupo de servidores piloto de Lync Server 2013, debe realizar la transición de la ruta de federación de los servidores perimetrales de Lync Server 2010 a la ruta de federación de los servidores perimetrales de Lync Server 2013.

Utilice los siguientes procedimientos para realizar la transición de la ruta de federación y la ruta de tráfico de medios del servidor perimetral y el director de Lync Server 2010 al servidor perimetral de Lync Server 2013, para una implementación en un único sitio.

> [!IMPORTANT]  
> Para cambiar la ruta de federación y la ruta de tráfico de medios, debe programar el tiempo de inactividad por mantenimiento para los servidores perimetrales de Lync Server 2013 y Lync Server 2010. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.



> [!IMPORTANT]  
> Si el servidor perimetral de Lync Server 2010 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, los procedimientos de esta sección no son compatibles. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, debe migrar primero todos sus usuarios de Lync Server 2010 a Lync Server 2013 y, a continuación, retirar el servidor perimetral de Lync Server 2010 antes de habilitar la federación en el servidor perimetral de Lync Server 2013.



> [!IMPORTANT]  
> Si su federación XMPP se enruta mediante un servidor perimetral de Lync Server 2013, los usuarios del Lync Server 2010 heredado no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se hayan trasladado a Lync Server 2013, se hayan configurado los certificados y las directivas de XMPP, se haya configurado el socio federado XMPP en Lync Server 2013 y, por último, se hayan actualizado las entradas de DNS.



## Para quitar la asociación de federación heredada de los sitios de Lync Server 2013

1.  En el servidor front-end de Lync Server 2013, abra la topología existente en Topology Builder.

2.  En el panel izquierdo, desplácese al nodo del sitio, que se encuentra justo debajo de **Lync Server**.

3.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades** .

4.  En el panel izquierdo, seleccione **Ruta de federación** .

5.  En **Asignación de ruta de federación del sitio**, desactive la casilla **Habilitar federación SIP** para deshabilitar la ruta de federación a través del entorno de Lync Server 2010 heredado.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de federación](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de federación")

6.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

7.  En **Generador de topologías** , seleccione el nodo en primera posición **Lync Server** .

8.  En el menú **Acción** , haga clic en **Publicar topología** .

9.  Haga clic en **Siguiente** para completar el proceso de publicación y, después, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.

## Para configurar el servidor perimetral heredado como servidor perimetral no federado

1.  En el panel izquierdo, desplácese al nodo **Lync Server 2010** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades** .

3.  Seleccione **General** en el panel izquierdo.

4.  Desactive la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página.
    
    ![Editar propiedades, General, borrar Habilitar federación](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propiedades, General, borrar Habilitar federación")

5.  En el menú **Acción** , seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente** .

6.  Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

7.  Compruebe que está deshabilitada la federación en el servidor perimetral heredado.
    
    ![Generador de topologías, grupo de servidores perimetrales, federación deshabilitada](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, federación deshabilitada")

## Para configurar certificados en el servidor perimetral de Lync Server 2010

1.  Exporte el certificado externo del servidor proxy de acceso, con la clave privada, desde el servidor perimetral de Lync Server 2010 heredado.

2.  En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.

3.  Asigne el certificado externo del servidor proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.

4.  El certificado de la interfaz interna del servidor perimetral de Lync Server 2013 se debe solicitar a una CA de confianza y asignar.

## Para cambiar la ruta de federación de Lync Server 2010 y usar el servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades** .

3.  Seleccione **General** en el panel izquierdo.

4.  Active la entrada de la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, seleccione **Aceptar** para cerrar la página.
    
    ![Cuadro de diálogo Editar propiedades, página General](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página General")

5.  En el menú **Acción** , seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente** .

6.  Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

7.  Compruebe que **Federación (puerto 5061)** está **Habilitado**.
    
    ![Generador de topologías, grupo de servidores perimetrales, federación habilitada](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, federación habilitada")

## Para actualizar al próximo salto de la federación del servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que se muestra y, a continuación, haga clic en **Editar propiedades** .

3.  En la página **General** , en **Selección de próximo salto** , seleccione en la lista desplegable el grupo de servidores  Lync Server 2013.
    
    ![Cuadro de diálogo Editar propiedades, página Próximo salto](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Próximo salto")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  En **Generador de topologías** , seleccione el nodo en primera posición **Lync Server** .

6.  En el menú **Acción** , haga clic en **Publicar topología** y complete el asistente.

## Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al grupo de servidores debajo de **Servidores front-end Standard Edition** o **Grupos de servidores front-end Enterprise Edition** .

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades** .

3.  En la sección **Asociaciones** , seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)** .
    
    ![Editar propiedades, General, Asociar grupos de servidores perimetrales](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propiedades, General, Asociar grupos de servidores perimetrales")

4.  En el cuadro de la lista desplegable, seleccione el servidor perimetral de Lync Server 2013.

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

## Para activar la federación del servidor perimetral de Lync Server 2013

1.  En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.

2.  Expanda el nodo, haga clic con el botón secundario en el Servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades** .
    

    > [!NOTE]
    > La federación solo se puede habilitar para un Grupo de servidores perimetrales único. Si tiene varios grupos de servidores perimetrales, seleccione uno para usar como Grupo de servidores perimetrales federado.



3.  En la página **General** , compruebe que está activada la opción de configuración **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** .
    
    ![Cuadro de diálogo Editar propiedades, página General](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página General")

4.  Haga clic en **Aceptar** para cerrar la página Editar propiedades.

5.  A continuación, navegue hasta el nodo del sitio.

6.  Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades** .

7.  En el panel izquierdo, haga clic en **Ruta de federación** .

8.  En **Asignación de ruta de federación del sitio** , seleccione **Habilitar federación SIP** y, a continuación, seleccione en la lista el Lync Server 2013  Servidor perimetral que se muestra.
    
    ![Editar propiedades, página Ruta de federación](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propiedades, página Ruta de federación")

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .
    
    Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.

## Para publicar cambios de configuración en el servidor perimetral

1.  En **Generador de topologías** , seleccione el nodo en primera posición **Lync Server** .

2.  En el menú **Acción** , haga clic en **Publicar topología** y complete el asistente.

3.  Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    

    > [!NOTE]
    > Es posible que aparezca el mensaje siguiente:<BR><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión más reciente del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Lync Server y compruebe que, en el registro SRV de DNS externo, se enumeran todos los servidores perimetrales habilitados para federación.</STRONG><BR>Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.



## Para configurar un servidor perimetral de Lync Server 2013

1.  Conecte todos los servidores perimetrales de Lync Server 2013.

2.  Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de cargas del hardware con el fin de enviar tráfico SIP para acceso (por lo general, el puerto 443) y federación (por lo general, el puerto 5061) al  Lync Server 2013  Servidor perimetral, en lugar del Servidor perimetral heredado.
    

    > [!NOTE]
    > Si no tiene un equilibrador de carga de hardware, debe actualizar el registro DNS A para la federación, de modo que se resuelva en el nuevo servidor perimetral de acceso de Lync Server. La manera de lograrlo que produce menos interrupciones es reducir el valor de TTL del FQDN del servidor perimetral de acceso de Lync Server externo, de modo que, cuando DNS se actualice para apuntar al nuevo servidor perimetral de acceso de Lync Server, la federación y el acceso remoto se actualizarán rápidamente.



3.  A continuación, detenga el **servidor perimetral de acceso de Lync Server** en cada equipo con el Servidor perimetral.

4.  En cada equipo con el Servidor perimetral heredado, abra el applet **Servicios** en **Herramientas administrativas** .

5.  En la lista de servicios, busque **Servidor perimetral de acceso de Lync Server** .

6.  Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.

7.  Establezca el Tipo de inicio en **Deshabilitado** .

8.  Haga clic en **Aceptar** para cerrar la ventana **Propiedades** .

