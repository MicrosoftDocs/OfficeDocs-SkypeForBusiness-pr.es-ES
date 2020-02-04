---
title: 'Lync Server 2013: Crear o editar proveedores federados de SIP públicos'
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
ms.openlocfilehash: 33303217e6e1a1fefb502f1e9b364a46adc85e02
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Crear o editar proveedores federados de SIP públicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de\!servicios de mensajería instantánea pública, como Windows Live Messenger, Yahoo y AOL.

Lync Server 2013 tiene configuraciones de proveedor público para America Online, Windows Live y Yahoo\! mensajería instantánea. Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.

Como configuración predeterminada, ninguno de los proveedores públicos está habilitado. Debe completar el contrato de licencia y el aprovisionamiento antes de habilitar los proveedores públicos. Puede habilitar el proveedor antes de completar el trabajo de licencias y aprovisionamiento. Los usuarios no podrán comunicarse con los contactos de esos proveedores hasta que se haya completado el trabajo previo. Para obtener más información sobre las licencias y el aprovisionamiento de proveedores públicos, vea [configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Use el procedimiento siguiente para crear o editar proveedores públicos:

<div>

## <a name="to-create-or-edit-public-providers"></a>Para crear o editar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en **proveedores federados SIP**.

4.  Si necesita crear un proveedor público nuevo, haga clic en **nuevo** y, a continuación, haga clic en **proveedor público**.

5.  Si necesita modificar una entrada de la lista de proveedores públicos, seleccione un proveedor público, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor federado de SIP** , puede escribir o modificar las siguientes opciones de configuración:
    
      - **Habilitar las comunicaciones con este proveedor**   al seleccionar esta opción, se habilita la mensajería instantánea con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad obligatoria, escriba el nombre del proveedor, ya que se reflejará en la lista de proveedores federados SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando. Esta información se proporciona como un elemento predeterminado y solo se debe cambiar si el proveedor público realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor público.
    
      - **Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir que los usuarios se comuniquen con personas de su lista de contactos que usan este proveedor** , limitará la comunicación a los contactos que haya aceptado y estarán en su lista de contactos.
        
        Si selecciona **permitir que los usuarios se comuniquen con todos los usuarios con este proveedor** , se eliminará la restricción que debe haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede comunicarse contigo desde la red del proveedor público.

7.  Cuando haya terminado de configurar la configuración, haga clic en **confirmar** para guardar o en **Cancelar** para descartar los cambios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

