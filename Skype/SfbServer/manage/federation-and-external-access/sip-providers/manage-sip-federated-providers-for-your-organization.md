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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo configurar la admisión de proveedores federados de los usuarios de SIP.
ms.openlocfilehash: 64b5dcd657b72f03b25fe6de2ff6c0cda21b676d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903182"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Administrar los proveedores federados SIP para su organización en Skype para Business Server

Para configurar la compatibilidad para los usuarios de SIP proveedores federados, debe hacer lo siguiente:

  - Configurar una o varias directivas de acceso de usuarios externos para admitir la comunicación con los contactos de proveedores federados SIP

  - Especificar los proveedores hospedados que desea admitir

  - Especificar los proveedores de mensajería instantánea públicos que desea admitir

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores federados SIP pública en Skype para Business Server

Conectividad de mensajería instantánea pública permite a los usuarios de su organización utilizar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por proveedores públicos.

Skype para Business Server tiene las configuraciones de proveedor público para la mensajería instantánea. Cada proveedor público se configura con el nombre de dominio completo de servidor perimetral del proveedor y el nivel de comprobación predeterminado **Permitir a los usuarios comunicarse únicamente con las personas en su lista de contactos que usa este proveedor**.

Como un valor predeterminado, ninguno de los proveedores públicos están habilitada. Debe completar el contrato de licencia y el aprovisionamiento de trabajo antes de habilitar a los proveedores públicos. Puede habilitar al proveedor antes de completar la concesión de licencias y trabajo de aprovisionamiento. Los usuarios no podrán comunicarse con los contactos en esos proveedores hasta que se complete el trabajo de requisito previos. Para obtener información detallada sobre licencias y aprovisionamiento de los proveedores públicos, vea [Configurar directivas para controlar el acceso de usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md).

Use el procedimiento siguiente para crear o cambiar proveedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para crear o editar proveedores públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Proveedores federados SIP**.

4.  Si necesita crear un nuevo proveedor público, haga clic en **nuevo** y, a continuación, haga clic en **proveedor público**.

5.  Si necesita editar una entrada de la lista de proveedores públicos, seleccione un proveedor público, haga clic en **Editar**, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado** , puede escribir o editar los valores siguientes:
    
      - **Habilitar las comunicaciones con este proveedor**   al seleccionar esta configuración permite la mensajería instantánea con usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad necesaria, el tipo, el nombre del proveedor como se reflejará en el listado de proveedores federados SIP.
    
      - **Servicio perimetral (FQDN) de acceso:**   una propiedad necesaria, escriba el nombre de dominio completo del servicio de servidor perimetral de acceso del proveedor del que se va a configurar. Esta información se proporciona como un elemento de forma predeterminada y sólo se puede cambiar si el proveedor público realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor público.
    
      - **Nivel de comprobación predeterminado:**   la configuración predeterminada, **Permitir a los usuarios comunicarse con personas en su lista de contactos que usa este proveedor** limitará la comunicación a los contactos que se han aceptado y se encuentran en la lista de contactos.
        
        Selección de **Permitir a los usuarios comunicarse con todos los usuarios con este proveedor** , quita la restricción que debe ha recibido y aceptado una invitación de contacto. Esta opción no limitar quién puede en contacto con usted desde la red del proveedor público.

7.  Cuando haya configurar las opciones, haga clic en **Confirmar** para guardar, o haga clic en **Cancelar** para descartar los cambios.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Crear o editar proveedores SIP federado hospedados en Skype para Business Server

Hospedado proveedor (IM) conectividad permite a los usuarios de la organización para usar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por proveedores hospedados de mensajería instantánea.

Cada proveedor hospedado está configurado con el nombre de dominio completo de servidor perimetral del proveedor y el nivel de comprobación predeterminado **Permitir a los usuarios comunicarse únicamente con las personas en su lista de contactos que usa este proveedor**.

Utilice el procedimiento siguiente para crear o editar proveedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para crear o editar proveedores hospedados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Proveedores federados SIP**.

4.  Si necesita crear un nuevo proveedor hospedado, haga clic en **nuevo** y, a continuación, haga clic en **proveedor hospedado**.

5.  Si necesita editar una entrada de la lista de proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar**, a continuación, haga clic en **Mostrar detalles**.

6.  En la página **Editar proveedor SIP federado** , puede escribir o editar los valores siguientes:
    
      - **Habilitar las comunicaciones con este proveedor**   al seleccionar esta configuración habilita la comunicación con los usuarios de este proveedor.
    
      - **Nombre del proveedor:**   una propiedad necesaria, el tipo, el nombre del proveedor como se reflejará en el listado de proveedores federados SIP.
    
      - **Servicio perimetral (FQDN) de acceso:**   una propiedad necesaria, escriba el nombre de dominio completo del servicio de servidor perimetral de acceso del proveedor hospedado que está configurando. Esta información debe ser proporcionada por el proveedor hospedado y sólo se puede cambiar si el proveedor hospedado realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor hospedado.
    
      - **Nivel de comprobación predeterminado:**   la configuración predeterminada, **Permitir a los usuarios comunicarse con personas en su lista de contactos que usa este proveedor** limitará la comunicación a los contactos que se han aceptado y se encuentran en la lista de contactos.
        
        Selección de **Permitir a los usuarios comunicarse con todos los usuarios con este proveedor** , quita la restricción que debe ha recibido y aceptado una invitación de contacto. Esta opción no limitar quién puede en contacto con usted desde la red del proveedor hospedado.

7.  Cuando haya configurar las opciones, haga clic en **Confirmar** para guardar, o haga clic en **Cancelar** para descartar los cambios.


## <a name="see-also"></a>Vea también


[Configurar directivas para controlar el acceso de usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

