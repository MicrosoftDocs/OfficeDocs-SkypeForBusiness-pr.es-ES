---
title: 'Lync Server 2013: crear o editar proveedores federados de SIP públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8a8da9937e31f0544dd93b1994745dc3a9eb10b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Crear o editar proveedores federados de SIP públicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La conectividad de mensajería instantánea pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por los proveedores de servicios de\!mensajería instantánea públicos, como Windows Live Messenger, Yahoo y AOL.

Lync Server 2013 tiene configuraciones de proveedor público para America Online, Windows Live y Yahoo\! mensajería instantánea. Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **permite a los usuarios comunicarse sólo con las personas de su lista de contactos que usan este proveedor**.

Como configuración predeterminada, no está habilitado ninguno de los proveedores públicos. Debe rellenar el contrato de licencia y proporcionar el trabajo antes de habilitar los proveedores públicos. Puede habilitar al proveedor antes de completar la licencia y proporcionar el trabajo. Los usuarios no podrán comunicarse con los contactos de estos proveedores hasta que haya finalizado el trabajo como requisito previo. Para obtener más información sobre la concesión de licencias y el aprovisionamiento de proveedores públicos, vea [Configure Policies to control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Use el siguiente procedimiento para crear o cambiar proveedores públicos.

<div>

## <a name="to-create-or-edit-public-providers"></a>Para crear o cambiar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.

4.  Si necesita crear un nuevo proveedor público, haga clic en **Nuevo** y luego en **Proveedor público**.

5.  Si desea cambiar una entrada de la lista de los proveedores públicos, seleccione un proveedor público, haga clic en **Editar** y luego en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:
    
      - **Habilitar comunicaciones con este proveedor**   : al seleccionar esta opción, se permite la mensajería instantánea con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad necesaria, escriba el nombre del proveedor tal y como se reflejará en la lista de proveedores federados SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   una propiedad necesaria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando. Esta información se proporciona como un elemento predeterminado y debe cambiarse solo si el proveedor cambia el FQDN del servicio perimetral de acceso en el proveedor de público.
    
      - **Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir a los usuarios comunicarse con personas de su lista de contactos que utilizan este proveedor** , limitará la comunicación a los contactos que haya aceptado y que se encuentren en su lista de contactos.
        
        La activación de **Permitir a los usuarios comunicarse con todos los que usan este proveedor** elimina la restricción que debe haber recibido y aceptado como una invitación de contacto. Este parámetro no limita quién puede comunicarse con usted desde la red del proveedor público.

7.  Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

