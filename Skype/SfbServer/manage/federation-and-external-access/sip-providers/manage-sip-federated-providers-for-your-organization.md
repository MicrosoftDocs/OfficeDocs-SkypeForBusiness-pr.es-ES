---
title: Administrar proveedores federados SIP para la organización
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre cómo configurar la compatibilidad con usuarios de proveedores federados SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823570"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Administrar proveedores federados SIP para su organización en Skype Empresarial Server

Para configurar la admisión de los usuarios de proveedores federados de SIP, realice las acciones siguientes:

  - Configurar una o varias directivas de acceso de usuarios externos para admitir la comunicación con los contactos de proveedores federados de SIP

  - Especificar los proveedores hospedados que desea admitir

  - Especificar los proveedores de MI públicos que desea admitir

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores federados SIP públicos en Skype Empresarial Server

La conectividad de mensajería instantánea (MI) pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores públicos.

Skype Empresarial Server tiene configuraciones de proveedor público para mensajería instantánea. Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de comprobación predeterminado Permite a los usuarios comunicarse solo con personas de su lista de contactos que usan **este proveedor.**

Como configuración predeterminada, no está habilitado ninguno de los proveedores públicos. Debe rellenar el contrato de licencia y proporcionar el trabajo antes de habilitar los proveedores públicos. Puede habilitar al proveedor antes de completar la licencia y proporcionar el trabajo. Los usuarios no podrán comunicarse con los contactos de estos proveedores hasta que haya finalizado el trabajo como requisito previo. Para obtener más información sobre la concesión de licencias y el aprovisionamiento de proveedores públicos, vea Configurar directivas para controlar la [obtención de acceso de usuarios públicos.](../external-access-policies/configure-policies-to-control-public-user-access.md)

Use el siguiente procedimiento para crear o editar proveedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para crear o cambiar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.

4.  Si necesita crear un nuevo proveedor público, haga clic en **Nuevo** y luego en **Proveedor público**.

5.  Si desea cambiar una entrada de la lista de los proveedores públicos, seleccione un proveedor público, haga clic en **Editar** y luego en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:
    
      - **Habilitar comunicaciones con este proveedor:**    la selección de este parámetro permite la mensajería instantánea con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**    Una propiedad necesaria, escriba el nombre del proveedor como se reflejará en el listado de Proveedores federados de SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   Una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando. Esta información se proporciona como un elemento predeterminado y debe cambiarse solo si el proveedor cambia el FQDN del servicio perimetral de acceso en el proveedor de público.
    
      - **Nivel de comprobación predeterminado:**    el parámetro predeterminado, **Permitir a los usuarios comunicarse con las personas de su lista de contactos que usan este proveedor** limitará la comunicación a los contactos que han aceptado y están en la lista de contactos.
        
        La activación de **Permitir a los usuarios comunicarse con todos los que usan este proveedor** elimina la restricción que debe haber recibido y aceptado como una invitación de contacto. Este parámetro no limita quién puede comunicarse con usted desde la red del proveedor público.

7.  Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores federados SIP hospedados en Skype Empresarial Server

La conectividad de mensajería instantánea (MI) del proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados.

Cada proveedor hospedado se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **Permitir a los usuarios comunicarse solamente con personas de su Lista de contactos que utilizan este proveedor**.

Use el siguiente procedimiento para crear o editar proveedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para crear o editar proveedores hospedados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, en **Proveedores federados de SIP**.

4.  Si necesita crear un nuevo proveedor hospedado, haga clic en **Nuevo** y, a continuación, haga clic en **Proveedor hospedado**.

5.  Si necesita editar una entrada de la lista de Proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor federado de SIP**, puede escribir o editar la siguiente configuración:
    
      - **Habilitar comunicaciones con este proveedor**   Al seleccionar esta configuración se habilita la comunicación con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**    Una propiedad necesaria, escriba el nombre del proveedor como se reflejará en el listado de Proveedores federados de SIP.
    
      - **Servicio perimetral de acceso (FQDN):**   Una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando. Esta información debe ser proporcionada por el proveedor hospedado y solo debe modificarse si el proveedor hospedado realiza un cambio al FQDN del servicio perimetral de acceso del proveedor hospedado.
    
      - **Nivel de verificación predeterminado:**    La configuración predeterminada, **Permitir a los usuarios comunicarse con personas de su Lista de contactos que utilizan este proveedor**, limitará la comunicación a los contactos que haya aceptado y estén en su lista de contactos.
        
        Seleccionar **Permitir a los usuarios comunicarse con todos los que utilizan este proveedor** elimina la restricción de tener que haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede contactarlo desde la red del proveedor hospedado.

7.  Cuando haya terminado de configurar los parámetros, haga clic en **Confirmar** para guardar o haga clic en **Cancelar** para descartar los cambios.


## <a name="see-also"></a>Vea también


[Configurar directivas para controlar la a acces de usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

