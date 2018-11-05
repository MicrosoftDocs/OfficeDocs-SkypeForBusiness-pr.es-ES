---
title: "Lync Server 2013 : Créa. ou modification des fournisseurs fédérés SIP hébergés"
TOCTitle: Crear o editar proveedores federados de SIP hospedados
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ552445(v=OCS.15)
ms:contentKeyID: 49115265
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o editar proveedores federados de SIP hospedados en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

La conectividad de mensajería instantánea (IM) del proveedor de servicios hospedados permite a los usuarios de su organización utilizar la mensajería instantánea para comunicarse con usuarios de servicios de mensajería instantánea ofrecidos por proveedores de servicios hospedados, como el Microsoft Office 365 y Lync Online.

Cada proveedor hospedado se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **Permitir a los usuarios comunicarse solamente con personas de su Lista de contactos que utilizan este proveedor**.

Utilice los siguientes procedimientos para crear o editar proveedores hospedados:

## Para crear o editar proveedores hospedados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.

4.  Si necesita crear un nuevo proveedor hospedado, haga clic en **Nuevo** y, a continuación, haga clic en **Proveedor hospedado**.

5.  Si necesita editar una entrada de la lista de Proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:
    
      - **Habilitar comunicaciones con este proveedor**   Al seleccionar esta configuración se habilita la comunicación con los usuarios de este proveedor.
    
      - **Nombre de proveedor:**   es una propiedad necesaria. Escriba el nombre del proveedor que se reflejará en la lista de proveedores SIP federados.
    
      - **Servicio perimetral de acceso (FQDN):**   Una propiedad necesaria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando. Esta información debe ser proporcionada por el proveedor hospedado y solo debe modificarse si el proveedor hospedado realiza un cambio al FQDN del servicio perimetral de acceso del proveedor hospedado.
    
      - **Nivel de comprobación predeterminado:**   el parámetro predeterminado, **Permitir a los usuarios comunicarse con las personas de su lista de contactos que usan este proveedor** limitará la comunicación a los contactos que han aceptado y están en la lista de contactos.
        
        Seleccionar **Permitir a los usuarios comunicarse con todos los que utilizan este proveedor** elimina la restricción de tener que haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede contactarlo desde la red del proveedor hospedado.

7.  Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.

## Vea también

#### Tareas

[Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

