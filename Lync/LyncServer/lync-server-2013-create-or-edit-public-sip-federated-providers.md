---
title: "Lync Server 2013 : Créa. ou modification des fournisseurs fédérés SIP publics"
TOCTitle: Crear o editar proveedores federados de SIP públicos
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48275270
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o editar proveedores federados de SIP públicos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

La conectividad de mensajería instantánea pública permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública, incluido Windows Live Messenger, Yahoo\! y AOL.

Lync Server 2013 tiene configuraciones de proveedor público de mensajería instantánea de America Online, Windows Live y Yahoo\!. Cada proveedor público está configurado con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de comprobación predeterminado **Permitir a los usuarios comunicarse solo con las personas de su lista de contactos que usan este proveedor** .

Como configuración predeterminada, no está habilitado ninguno de los proveedores públicos. Debe rellenar el contrato de licencia y proporcionar el trabajo antes de habilitar los proveedores públicos. Puede habilitar al proveedor antes de completar la licencia y proporcionar el trabajo. Los usuarios no podrán comunicarse con los contactos de estos proveedores hasta que haya finalizado el trabajo como requisito previo. Para más información sobre licencias y proporcionar proveedores públicos, vea [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Use el siguiente procedimiento para crear o cambiar proveedores públicos.

## Para crear o cambiar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.

4.  Si necesita crear un nuevo proveedor público, haga clic en **Nuevo** y luego en **Proveedor público**.

5.  Si desea cambiar una entrada de la lista de los proveedores públicos, seleccione un proveedor público, haga clic en **Editar** y luego en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:
    
      - **Habilitar comunicaciones con este proveedor:**   la selección de este parámetro permite la mensajería instantánea con los usuarios de este proveedor.
    
      - **Nombre de proveedor:**   es una propiedad necesaria. Escriba el nombre del proveedor que se reflejará en la lista de proveedores SIP federados.
    
      - **Servicio perimetral de acceso (FQDN):**    es una propiedad necesaria. Escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando. Esta información se proporciona como un elemento predeterminado y debe cambiarse solo si el proveedor cambia el FQDN del servicio perimetral de acceso en el proveedor de público.
    
      - **Nivel de comprobación predeterminado:**    el parámetro predeterminado, **Permitir a los usuarios comunicarse con las personas de su lista de contactos que usan este proveedor** limitará la comunicación a los contactos que han aceptado y están en la lista de contactos.
        
        La activación de **Permitir a los usuarios comunicarse con todos los que usan este proveedor** elimina la restricción que debe haber recibido y aceptado como una invitación de contacto. Este parámetro no limita quién puede comunicarse con usted desde la red del proveedor público.

7.  Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.

## Vea también

#### Tareas

[Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

