---
title: 'Lync Server 2013: creación o edición de proveedores federados de SIP hospedados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937dfe2a63f755a7366fbb1b82c5593c466ac544
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Creación o edición de proveedores federados de SIP hospedados Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La conectividad de mensajería instantánea (mi) de proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados, incluidos Microsoft Office 365 y Lync Online.

Cada proveedor hospedado se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **Permitir a los usuarios comunicarse solamente con personas de su Lista de contactos que utilizan este proveedor**.

Utilice los siguientes procedimientos para crear o editar proveedores hospedados:

<div>

## <a name="to-create-or-edit-hosted-providers"></a>Para crear o editar proveedores hospedados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, en **Proveedores federados de SIP**.

4.  Si necesita crear un nuevo proveedor hospedado, haga clic en **Nuevo** y, a continuación, haga clic en **Proveedor hospedado**.

5.  Si necesita editar una entrada de la lista de Proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor federado de SIP**, puede escribir o editar la siguiente configuración:
    
      - **Habilitar comunicaciones con este proveedor**   : al seleccionar esta opción, se habilitan las comunicaciones con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad necesaria, escriba el nombre del proveedor tal y como se reflejará en la lista de proveedores federados SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   una propiedad necesaria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que va a configurar. Esta información debe ser proporcionada por el proveedor hospedado y solo debe modificarse si el proveedor hospedado realiza un cambio al FQDN del servicio perimetral de acceso del proveedor hospedado.
    
      - **Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir a los usuarios comunicarse con personas de su lista de contactos que utilizan este proveedor** , limitará la comunicación a los contactos que haya aceptado y que se encuentren en su lista de contactos.
        
        Seleccionar **Permitir a los usuarios comunicarse con todos los que utilizan este proveedor** elimina la restricción de tener que haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede contactarlo desde la red del proveedor hospedado.

7.  Cuando haya terminado de configurar los parámetros, haga clic en **Confirmar** para guardar o haga clic en **Cancelar** para descartar los cambios.

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

