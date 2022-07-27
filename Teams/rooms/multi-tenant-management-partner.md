---
title: Administración de clientes multiempresa para partners
author: donnah007
ms.author: v-donnahill
ms.date: 07/25/2022
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
description: Administración de clientes multiempresa para partners.
f1keywords: ''
ms.openlocfilehash: 23b0460d5f59830ea00522ac001b7f7524ad2f45
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024123"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Administración de clientes multiempresa para partners

La administración multiinquilino (MTM) del servicio administrado Salas de Teams (TRM) ayuda a las organizaciones asociadas a administrar varios clientes en un solo lugar, con sus propias credenciales de dominio. Los usuarios asociados solo verán los salones de cliente asignados para administrar. Es posible aplicar roles personalizados para cada cliente en el inquilino MTM, dando a las organizaciones asociadas un control granular de los permisos de los recursos del cliente. 

El portal MTM se puede acceder a través de este [link](https://partner.rooms.microsoft.com/).

> [!Note] 
> Las organizaciones asociadas no pueden administrar sus propios salones a través del portal MTM. Estos salones se pueden administrar en el [portal de TRM](https://portal.rooms.microsoft.com/). 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Requisitos previos para administrar a sus clientes a través de la experiencia MTM

Para obtener acceso al portal de MTM, su organización debe incorporarse como socio Elite para el servicio TRM. Para convertirte en un socio elite, ponte en contacto con askelite@microsoft.com.

## <a name="on-boarding-customers"></a>Clientes que se alojen en el alojamiento

Para administrar clientes a través del portal de TRM-MTM, debe establecerse una relación entre el inquilino de la organización asociada y el cliente a través de una invitación enviada por el cliente. 

## <a name="tenant-managers"></a>Administradores de inquilinos

Este rol integrado solo se puede configurar en el portal TRM-MTM. Este rol le permite asignar un grupo de usuarios que acepten invitaciones, pero que no participen en la administración de salones de cliente. Se recomienda configurar el rol. De lo contrario, solo los usuarios con el rol administrador de servicios administrados en su inquilino podrán aceptar invitaciones.

**Para configurar administradores de inquilinos**
 
1.  Inicie sesión en el portal de TRM-MTM como administrador global o administrador de servicios administrados.
2.  Vaya a Administradores de inquilinos.
3.  Seleccione **Agregar administradores de inquilinos**.
4.  En el panel de detalles, busque los usuarios o grupos de seguridad.
5.  Seleccione el usuario o el grupo.
6.  Seleccione **Agregar**.

### <a name="invitation-from-the-customer"></a>Invitación del cliente

El partner debe proporcionar el nombre de dominio a los clientes. Solo los roles de administrador global, administrador de servicios administrados y administradores de inquilinos pueden ver y aceptar la invitación al iniciar sesión en el portal de TRM-MTM. 

> [!Note]
> Aunque estos roles pueden ver invitaciones y metadatos de inquilino de alto nivel, no verá los datos del cliente hasta que se le asigne un rol con ese cliente.

Los detalles de la invitación del cliente se describen en [Administración multiinquilino para clientes](multi-tenant-management-customer.md).

**Para aceptar una invitación pendiente**

1. Inicie sesión en el portal de TRM-MTM como administrador global, administrador de servicios administrados o administrador de inquilinos.
1. Vaya a **Inquilinos**.
1. Seleccione la invitación que se muestra con el estado "Pendiente".
1. Revise los detalles de la invitación.
1. Asigne usuarios que serán los administradores principales de este cliente.
1. Selecciona **Aceptar** para establecer la relación entre partner y cliente.

   Al seleccionar **Denegar** , se elimina la invitación.

   > [!Note]
   > No hay ninguna asociación permanente con el usuario que acepte la invitación.

   > [!Note]
   > *Si la invitación se deniega accidentalmente, el cliente debe crear una nueva.* 

**Para revisar la configuración o agregar más administradores principales para un inquilino**

1. Selecciona el cliente en la lista **Inquilinos** .
1. En el panel de detalles, seleccione **Administradores principales**.
1. Busque el usuario o grupo.
1. Seleccione **Agregar** para confirmar la selección.

## <a name="off-boarding-customers"></a>Clientes que no se alojen

Para quitar a un cliente, debe quitarlo de la lista **Inquilinos** .

**Para quitar un cliente** 

1. Inicie sesión en el portal de TRM-MTM como administrador principal del cliente que desea quitar.
1. Vaya a **Inquilinos**.
1. Selecciona el cliente que quieras quitar.
1. En el panel de detalles del cliente, selecciona **Quitar cliente**.
1. Seleccione **Eliminar** en el aviso de confirmación para finalizar la asociación entre usted y el inquilino del cliente.

## <a name="managing-partner-roles"></a>Administrar roles de partner

Los roles de partner permiten la delegación de responsabilidades a personal adicional. El concepto de estos roles es el mismo que se describe en [Control de acceso basado](microsoft-teams-rooms-premium-rbac.md) en roles, pero en el contexto de cada cliente. Además, es importante tener en cuenta que los roles de partner son distintos de los roles del cliente. El cliente puede eliminar los roles de partner. 

El rol **Administradores principales** es el único rol integrado para cada cliente integrado y tiene casi todos los permisos para el servicio TRM (vea la tabla 1, en el contexto del cliente). Los permisos de rol de partner** solo se extienden hasta las salas designadas por el cliente. Por ejemplo, si el cliente es una organización global y asigna al partner la administración de todos los salones de Ee. UU., el administrador principal solo podrá administrar y delegar los permisos de esos salones. El Partner no tiene visibilidad para otras salas que el Cliente puede tener en otros países. 

**Para administrar usuarios en el rol **partner** de un cliente**

1. Vaya a **Configuración > Roles**. 
1. Seleccione el cliente en la lista desplegable para la que desea editar el rol de partner.
1. Seleccione el rol integrado **Administradores** principales de la lista.
1. Seleccione **Tareas.**
1. En la lista, seleccione **Administradores asignados.**
1. Seleccione **Miembros.**
1. Seleccione **Editar.** 
1. Busca el usuario o grupo de seguridad que quieras agregar en la barra de búsqueda.
1. Seleccione el usuario o el grupo.
1. Seleccione **Guardar** para confirmar los cambios.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Administrar roles de partner personalizados para un cliente

Como partner, puede crear roles personalizados que se adapten a sus requisitos operativos. Por ejemplo, puede crear un rol de departamento de soporte técnico que solo tenga permisos de administración de incidentes. 

**Para administrar roles**

1. Vaya a **Configuración > Roles**. 
1. Seleccione el cliente en el menú desplegable para el que desea editar el rol de partner.
1. Cree un [rol personalizado](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Característica|Permiso|**Administración MMR**|**Cliente potencial del sitio**|**Site Tech**|**Administradores principales**|
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

> [!Note]
> Un usuario asignado como administrador principal del cliente A tiene permisos completos en el servicio TRM solo para ese cliente. Los permisos del usuario en el Cliente A no afectan a otros clientes.

## <a name="security"></a>Seguridad

Los clientes finales conservan el control sobre el acceso a sus datos y pueden quitar por completo un partner o roles específicos en cualquier momento.

Con la característica de acceso delegado, un partner no obtiene ningún otro privilegio fuera del portal de servicios TRM. Por ejemplo, al usar esta característica para invitar a un partner a administrar salas en el servicio TRM, no se conceden permisos a AAD ni al Centro de Administración de Teams ni a ningún otro producto de Microsoft. Además, los partners no tienen acceso para ver o modificar salas no definidas en el ámbito de la invitación.

Una vez establecido el partner (relación con el cliente), como se describe en "Clientes de incorporación" de este documento, el partner puede ver los datos de sala en el servicio TRM. Esto incluye todos los datos presentes en el servicio TRM, pero derivados de otros productos de Microsoft. Por ejemplo, los informes de calidad de llamadas en el portal TRM se derivan de datos de calidad de llamadas de Teams.

Los datos residen en el inquilino del cliente y no se copian en el inquilino del partner. 

El portal MTM utiliza la autenticación AAD para validar las credenciales de inicio de sesión del partner. Es importante tener en cuenta que, en este momento, las directivas de autenticación del cliente no se aplicarán al partner. Por ejemplo, si el cliente tiene una directiva de autenticación multifactor, no se traduce al partner.

El cliente puede extraer registros de auditoría para el servicio TRM, que incluye la actividad de partners. Consulte [Registro de auditoría en el servicio administrado de Salas de Teams](multi-tenant-auditing.md).

> [!Note]
> La auditoría de AAD y la auditoría de O365 no captura registros del portal de TRM.

## <a name="navigating-the-mtm-portal"></a>Navegar por el portal MTM

El portal MTM tiene dos modelos interactivos para navegar entre los datos del cliente:

- Vistas de agregado en las que los datos de todos los clientes se consolidan en una sola lista y se pueden filtrar.

  > [!Note]
  > Esta vista solo se admite en la página **Incidentes** cuando **la vista Habilitar todos los vales** está activada.
  >
  > ![Figura 1](../media/multi-tenant-management-partner-001.png)

 - Cambio de inquilino donde solo se muestran los datos del **cliente** seleccionado en la lista desplegable.
