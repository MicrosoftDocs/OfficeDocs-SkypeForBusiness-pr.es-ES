---
title: Administrar proveedores federados SIP para la organización
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Aprenda a configurar soporte técnico para los usuarios de proveedores federados de SIP.
ms.openlocfilehash: ee16ec8953a722a86838f710fdf92cb9b2ce5f36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303966"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Administrar proveedores federados de SIP para su organización en Skype empresarial Server

Para configurar el soporte técnico a los usuarios de proveedores federados de SIP, debe hacer lo siguiente:

  - Configurar una o más directivas de acceso de usuarios externos para admitir la comunicación con contactos de proveedores federados de SIP

  - Especificar qué proveedores alojados desea admitir

  - Especificar los proveedores de mensajería instantánea pública que desea admitir

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores federados de SIP pública en Skype empresarial Server

La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores públicos.

Skype empresarial Server tiene configuraciones de proveedor público para la mensajería instantánea. Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.

Como configuración predeterminada, ninguno de los proveedores públicos está habilitado. Debe completar el contrato de licencia y el aprovisionamiento antes de habilitar los proveedores públicos. Puede habilitar el proveedor antes de completar el trabajo de licencias y aprovisionamiento. Los usuarios no podrán comunicarse con los contactos de esos proveedores hasta que se haya completado el trabajo previo. Para obtener más información sobre las licencias y el aprovisionamiento de proveedores públicos, vea [configurar directivas para controlar el accesible a los usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md).

Use el procedimiento siguiente para crear o editar proveedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para crear o editar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

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

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores federados de SIP alojados en Skype empresarial Server

La conectividad de mensajería instantánea (mi) de proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados.

Cada proveedor alojado se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.

Use el procedimiento siguiente para crear o editar proveedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para crear o editar proveedores hospedados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en **proveedores federados SIP**.

4.  Si necesita crear un nuevo proveedor alojado, haga clic en **nuevo** y, a continuación, haga clic en **proveedor hospedado**.

5.  Si necesita modificar una entrada de la lista de proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor federado de SIP** , puede escribir o modificar las siguientes opciones de configuración:
    
      - **Habilitar las comunicaciones con este proveedor**   al seleccionar esta opción se habilitan las comunicaciones con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad obligatoria, escriba el nombre del proveedor, ya que se reflejará en la lista de proveedores federados SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando. Esta información debe proporcionarla el proveedor hospedado y solo se debe cambiar si el proveedor hospedado realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor hospedado.
    
      - **Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir que los usuarios se comuniquen con personas de su lista de contactos que usan este proveedor** , limitará la comunicación a los contactos que haya aceptado y estarán en su lista de contactos.
        
        Si selecciona **permitir que los usuarios se comuniquen con todos los usuarios con este proveedor** , se eliminará la restricción que debe haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede ponerse en contacto contigo desde la red del proveedor alojado.

7.  Cuando haya terminado de configurar la configuración, haga clic en **confirmar** para guardar o en **Cancelar** para descartar los cambios.


## <a name="see-also"></a>Vea también


[Configurar directivas para controlar el accesible al usuario público](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

