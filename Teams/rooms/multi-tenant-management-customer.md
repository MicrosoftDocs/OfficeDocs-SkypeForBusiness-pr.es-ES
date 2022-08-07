---
title: Administración de partners para clientes
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.date: 06/09/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: administración de partners para los clientes.
f1keywords: ''
ms.openlocfilehash: 9ac7e01de1f9a9e620afa665298d8f3746319db2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271375"
---
# <a name="partner-management-for-customers"></a>Administración de partners para clientes

La administración de partners en el servicio Salas de Teams administrada (TRM) permite a los clientes delegar sin problemas el acceso y las responsabilidades a una o varias organizaciones asociadas. Los partners solo pueden administrar los salones que tienen asignados.

## <a name="on-boarding-partners"></a>Socios que se embarcan en el embarque
   Invite a partners a través del portal de TRM para establecer la relación entre su organización y el inquilino de la organización asociada.

### <a name="invitation-to-partner"></a>Invitación a partner

   En este método, debe conocer el nombre de dominio del partner (por ejemplo, Contoso.com).

**Para iniciar la invitación** 

1. Inicie sesión en el Portal administrado de Salas de Teams como administrador de servicios administrados.
1. Vaya a **Configuración >** **Partners** y, después, seleccione **Agregar partner.**
1. Escriba el nombre de dominio en la primera fila.
1. Configure el número de días hasta que expire la invitación escribiendo un entero entre 1 y 30.
1. Configure los eventos que requerirán una aprobación de control de cambios. De forma predeterminada, todos los controles están establecidos en **Aprobación automática.**

   > [!NOTE]
   > *Actualmente, solo la aprobación automática está disponible.*
   > 
   >  1.  *Aprobación manual:* Cuando el partner realiza la acción, se genera una solicitud de aprobación para que el cliente la revise y apruebe. La acción no se implementa hasta que se ha aprobado la solicitud.
   >  
   >  1. *Aprobación automática:* Cuando el partner realiza la acción, no se genera ninguna solicitud de aprobación y la acción se implementa inmediatamente.
     
1. Seleccione **Siguiente.**
1. Asigne las salas que administrará el partner y, después, seleccione **Siguiente.**
1. Para continuar, revisa los términos y selecciona **Acepto.**
1. Revise los detalles de la invitación.
1. Seleccione **Agregar partner** para enviar la invitación.

La invitación se envía a los administradores de inquilinos en la instancia del partner para su revisión. El primer usuario asociado que acepte la invitación establecerá el vínculo entre el partner y el inquilino y asignará administradores principales. No hay ninguna asociación especial con el usuario que establece el enlace, lo que permite flexibilidad si se reasigna al usuario. Siempre debe haber al menos un usuario en el rol de administrador principal.

Para administrar usuarios en el rol de administrador principal, consulte [Administración multiinquilino para partners](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Socios externos

**Para quitar un partner**

1. Inicie sesión en el portal TRM-MTM como administrador de MMR.
1. Vaya a **Configuración > Partners.**
1. Selecciona el partner que quieras quitar.
1. En el panel de detalles del cliente, selecciona **Quitar partner.**
1. Seleccione **Eliminar**. 
1. En el aviso de confirmación para finalizar la asociación entre usted y el inquilino del cliente, seleccione **Eliminar**.

## <a name="managing-partner-roles"></a>Administrar roles de partner

Los roles de partner permiten que su partner delegue responsabilidades más pormenorizadamente a personal adicional. El concepto de estos roles es el mismo que se describe en [Control de acceso basado en roles](microsoft-teams-rooms-premium-rbac.md). Es importante tener en cuenta que los roles de partner son distintos de los roles personalizados. 

El rol **administrador principal** es el único rol integrado para cada partner que agregue. Este rol tiene casi todos los permisos para los salones que asignó a ese partner para el servicio TRM (vea [la Tabla 1](#table-1)). Por ejemplo, si tiene salas en todo el mundo y asigna un partner para administrar todos los salones de Estados Unidos, el administrador principal solo podrá administrar y delegar los permisos de esos salones. En este caso, los administradores principales de este partner no tienen visibilidad para los salones fuera de ee. UU. 

### <a name="adding-primary-admins-to-partner"></a>Agregar administradores principales al partner

Si ya ha enviado una invitación a un partner y desea delegar más salones, puede agregar salas al rol de administrador de partner.

**Para agregar salas nuevas a un partner existente**

1. Inicie sesión en el portal TRM-MTM como administrador de MMR.
1. Vaya a **Configuración > Roles.**
1. Seleccione  **Roles de partner.** 
1. Seleccione el rol **de administrador principal** para el nombre del partner correspondiente.
1. En el panel de roles, seleccione **Asignaciones**.
1. Seleccione la tarea **Administradores asignados** .
1. En el panel de asignación Administradores asignados, seleccione **Ámbito**.
1. Seleccione **Editar**.
1. Busque las salas que desea agregar y seleccione la sala deseada.
1. Para confirmar los cambios, seleccione **Guardar**.

### <a name="table-1"></a>Tabla 1

|Característica|Permiso|**Administración MMR**|**Cliente potencial del sitio**|**Site Tech**|**Administrador del partner**|
| :- | :- | :- | :- | :- | :- |
|Habitaciones|Ver| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificar|&#10004;|&#10004;|&#10004;|&#10004;|
||Tecla Restablecer|&#10004;||||
||Clave de descarga|&#10004;|&#10004;|&#10004;||
||Anular la inscripción|&#10004;|&#10004;|&#10004;||
||Crear |&#10004;|&#10004;|||
|Administración de grupos|Ver|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;|||
||Crear |&#10004;|&#10004;|||
|Administración de anillos de actualización|Ver|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;||&#10004;|
|Informes|Ver|&#10004;|&#10004;||&#10004;|
||Crear incidente de cliente|&#10004;|&#10004;|&#10004;|&#10004;|
|Administración de entradas|Ver|&#10004;|&#10004;|&#10004;|&#10004;|
||Actualización|&#10004;|&#10004;|&#10004;|&#10004;|
|Configuración de MMR|Ver|&#10004;||||
||Modificar|&#10004;||||
|Administración de roles|Ver |&#10004;|||&#10004;|
||Modificar|&#10004;|||&#10004;|

## <a name="security"></a>Seguridad

Como cliente final, usted mantiene el control sobre el acceso a sus datos y puede quitar completamente un partner en cualquier momento. 

Con la característica de acceso delegado, un partner no obtiene ningún otro privilegio fuera del portal de servicios TRM. Sin embargo, todos los datos presentes en el servicio TRM derivados de otros productos de Microsoft se consideran datos en el servicio TRM. Por ejemplo, si bien los informes de calidad de llamadas se derivan de los datos de calidad de llamadas de Teams, cualquier dato del portal de TRM se encuentra en el ámbito de los permisos. 

No se conceden permisos a AAD, al Centro de Administración de Teams ni a ningún otro producto de Microsoft. Además, los partners no tienen acceso para ver o modificar salas no definidas en el ámbito de la invitación. 

Los datos residen en el inquilino del cliente y no se copian en el inquilino del partner. 

El portal de MTM usa la autenticación de Azure AD para validar las credenciales de inicio de sesión del partner. Tenga en cuenta que, en este momento, las directivas de autenticación del cliente no se aplican al partner. Por ejemplo, si el cliente tiene una directiva de autenticación multifactor, no se traduce al partner. 

Para obtener registros de la actividad de asociados, consulte [Auditoría](multi-tenant-auditing.md). 

> [!NOTE]
> La auditoría de AAD y la auditoría de O365 no capturan registros del portal de TRM. 
