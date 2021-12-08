---
title: Administración de partners para clientes
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: administración de partners para clientes.
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331267"
---
# <a name="partner-management-for-customers"></a>Administración de partners para clientes


La administración de partners en el servicio Salas de Teams administrado (TRM) permite a los clientes delegar sin problemas el acceso y las responsabilidades a una o varias organizaciones asociadas. Los partners solo pueden administrar los salas a los que están asignados. 

## <a name="on-boarding-partners"></a>Partners de a bordo
   Invite a partners a través del portal de TRM para establecer la relación entre su organización y el inquilino de la organización asociada. 

### <a name="invitation-to-partner"></a>Invitación a partner

   En este método, el partner debe proporcionar los *UPN* de los usuarios que serán los administradores principales asignados a usted. 

**Para iniciar la invitación** 

1. Inicie sesión en el Salas de Teams administrado como administrador de MMR.
1. Vaya a **Configuración >** **partners** y, a continuación, seleccione **Agregar partner.**
1. Escriba el nombre y el UPN de los administradores principales en la primera fila.
1. Seleccione **Agregar contacto** para confirmar.
1. Realice una de las siguientes acciones:
   - Para agregar otro usuario, repita el paso 4.
   - Para eliminar un usuario, seleccione el icono de papelera a la derecha del usuario.

    > [!NOTE]
    > No es posible usar grupos o listas de distribución, ya que la invitación está vinculada al UPN.

1. Seleccione **Siguiente.**
1. Configure los eventos que requerirán una aprobación de control de cambio. De forma predeterminada, todos los controles se establecen en **Aprobación automática.**

   > [!NOTE]
   > *Solo la aprobación automática está disponible por ahora.*
   > 
   >  1.  *Aprobación manual:* Cuando el partner realiza la acción, se genera una solicitud de aprobación para que el cliente la revise y apruebe. La acción no se implementa hasta que se haya aprobado la solicitud.
   >  
   >  1. *Aprobación automática:* Cuando el partner realiza la acción, no se genera ninguna solicitud de aprobación y la acción se implementa inmediatamente.
     
1. Seleccione **Siguiente.**
1. Asigne salas que administrará el partner y, a continuación, seleccione **Siguiente.**
1. Para continuar, revise los términos y seleccione **Acepto.**
1. Revise los detalles de la invitación.
1. Seleccione **Agregar partner** para enviar la invitación.

La invitación es única para cada usuario y es independiente. El primer usuario asociado que acepte la invitación establecerá el vínculo entre el partner y el inquilino. No hay ninguna asociación especial con el usuario que establezca el vínculo, lo que permite flexibilidad si el usuario se reasigna. Los usuarios siguientes que acepten se asignarán automáticamente al rol de administradores principales. Siempre debe haber al menos un usuario en el rol de administrador principal.

Para administrar usuarios en el rol de administrador principal, vea [Administración multiempresa para partners.](multi-tenant-management-partner.md)


## <a name="off-boarding-partners"></a>Partners que no se alojen

**Para quitar un partner**

1. Inicie sesión en el portal de TRM-MTM como administrador de MMR.
1. Vaya a Ir **a Configuración > asociados.**
1. Seleccione el partner que desea quitar.
1. En el panel de detalles del cliente, seleccione **Quitar partner.**
1. Seleccione **Eliminar**. 
1. En el mensaje de confirmación para finalizar la asociación entre su inquilino y el cliente, seleccione **Eliminar**.

## <a name="managing-partner-roles"></a>Administrar roles de partner

Los roles de partner permiten que su partner delegue responsabilidades de forma más granular a personal adicional. El concepto de estos roles es el mismo que se describe en Control de acceso [basado en roles.](microsoft-teams-rooms-premium-rbac.md) Es importante tener en cuenta que los roles de partner son distintos de los roles personalizados. 

El **rol de administrador** principal es el único rol integrado para cada partner que agregue. Este rol tiene casi todos los permisos para los salas que asignó a ese partner para el servicio TRM (vea [tabla 1).](#table-1) Por ejemplo, si tiene salas en todo el mundo y asigna un partner para administrar todos los salas de EE. UU., el administrador principal solo podrá administrar y delegar permisos para esos salas. En este caso, los administradores principales de este partner no tienen visibilidad en ninguna de las salas fuera de los Estados Unidos. 

### <a name="adding-primary-admins-to-partner"></a>Agregar administradores principales al partner

Si ya ha enviado una invitación a un partner y desea agregar más usuarios a ese administrador, puede agregarlos al rol de administrador del partner. De este modo, se envía una invitación a los usuarios agregados.

**Para agregar nuevos usuarios a un partner existente**

1. Inicie sesión en el portal de TRM-MTM como administrador de MMR.
1. Vaya a **Configuración > roles.**
1. Seleccione  **Roles de partner.** 
1. Seleccione el **rol de administrador principal** para el nombre de partner correspondiente.
1. En el panel de roles, seleccione **Tareas.**
1. Seleccione la **tarea Administradores invitados.** 
1. En el panel Tarea de administradores invitados, seleccione **Miembros.**
1. Seleccione **Editar**.
1. Escriba el UPN del nuevo usuario y seleccione **Agregar contacto.**
1. Para confirmar los cambios, seleccione **Guardar**.

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>Tabla 1

|Característica|Permiso|**Administrador de MMR**|**Cliente potencial del sitio**|**Site Tech**|**Administrador de partners**|
| :- | :- | :- | :- | :- | :- |
|Salas|Ver|||||
||Modificar|||||
||Tecla Restablecer|||||
||Clave de descarga|||||
||Desenrollar|||||
|Administración de grupos|Crear |||||
||Ver|||||
||Modificar|||||
|Actualizar la administración de anillos|Crear |||||
||Ver|||||
||Modificar|||||
|Informes|Ver|||||
|Administración de entradas|Crear un incidente de cliente|||||
||Ver|||||
||Actualización|||||
|Mmr Configuración|Ver|||||
||Modificar|||||
|Administración de roles|Ver |||||
||Modificar|||||





## <a name="security"></a>Seguridad

Como cliente final, conserva el control sobre el acceso a los datos y puede quitar por completo un partner en cualquier momento. 

Con la característica de acceso delegado, un partner no obtiene ningún otro privilegio fuera del portal de servicio de TRM. Sin embargo, los datos presentes en el servicio TRM derivados de otros productos de Microsoft se consideran datos en el servicio TRM. Por ejemplo, si bien los informes de calidad de llamadas se derivan Teams datos de calidad de llamadas, los datos del portal de TRM están en el ámbito de permisos. 

No se conceden permisos a AAD ni al Centro Teams administración ni a ningún otro producto de Microsoft. Además, los partners no tienen acceso a ver o modificar salas no definidas en el ámbito de invitación. 

Los datos residen en el inquilino del cliente y no se copian en el inquilino del partner. 

El portal MTM usa Azure AD autenticación para validar las credenciales de inicio de sesión del partner. Tenga en cuenta que, en este momento, las directivas de autenticación del cliente no se aplican al partner. Por ejemplo, si el cliente tiene una directiva de autenticación multifactor, no se traduce al partner. 

Para extraer registros de la actividad del partner, vea [Auditoría.](multi-tenant-auditing.md) 

> [!NOTE]
> AAD auditoría y auditoría de O365 no capturan registros del portal de TRM. 
