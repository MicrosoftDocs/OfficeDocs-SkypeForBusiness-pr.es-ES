---
title: 'Panel de control: búsqueda de usuarios actualizada'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Skype Empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También puede buscar usuarios mediante el Panel de control de Lync Server o el complemento Usuarios y equipos de Active Directory.
ms.openlocfilehash: f74c1dfe7f1b8184c59261ff03a01f2f5b39db18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820250"
---
# <a name="control-panel---updated-user-search"></a>Panel de control actualizado: Búsqueda de usuarios

Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Skype Empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También puede buscar usuarios mediante el Panel de control de Lync Server o el complemento Usuarios y equipos de Active Directory.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página Panel de control **de** búsqueda de usuarios:

- [Buscar usuarios](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Habilitar o deshabilitar usuarios](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Mover usuario](ms.lync.lscp.UserMove.md)

- [Mover todos los usuarios](ms.lync.lscp.UserMoveAll.md)

- [Asignar directivas a usuarios](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurar la federación, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública para los usuarios](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configurar telefonía para usuarios](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>Referencia de la UI

Las listas siguientes describen los menús, comandos, campos y propiedades de la página de **Búsqueda de usuarios**.

### <a name="user-search"></a>Búsqueda de usuarios

- **Búsqueda** Busque usuarios por la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario.

- **Búsqueda LDAP** Busque usuarios escribiendo una expresión LDAP.

- **Cuadro de búsqueda de usuarios** Escriba los datos de usuario o la expresión LDAP que desea buscar.

- **Buscar** Haga clic para mostrar los usuarios que coinciden con los valores de búsqueda especificados en el cuadro **Buscar usuarios.**

- **Abrir consulta** Haga clic para abrir una consulta de búsqueda guardada.

- **Guardar consulta** Haga clic para guardar una consulta de búsqueda.

- **+ Agregar filtro** Haga clic para agregar criterios de búsqueda adicionales.

- **Campos de filtro de búsqueda** Seleccione el campo en el que desea filtrar los resultados de la búsqueda, seleccione un operador para la consulta y, a continuación, escriba la cadena en la que desea buscar.

- **Número máximo de usuarios que se mostrarán** Escriba el número de resultados de búsqueda que desea mostrar o use las flechas arriba y abajo para especificar el número.

Agregar texto descriptivo adicional, según sea conveniente.

### <a name="search-results-menus"></a>Menús de búsqueda de resultados

- **Habilitar usuarios** Haga clic para abrir el cuadro de diálogo Usuarios: Nuevo usuario [de Lync Server,](ms.lync.lscp.UserNew.md) donde puede agregar un nuevo usuario a Skype Empresarial Server.

    Para agregar un nuevo contacto, haga clic en la flecha abajo y luego seleccione **Activar contactos** para abrir el cuadro de diálogo de [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Editar** Haga **clic en** Editar y, a continuación, en  Mostrar detalles para mostrar los detalles del usuario seleccionado o en Seleccionar todos los resultados de búsqueda para seleccionar todos los usuarios que se muestran en la tabla de resultados. 

- **Acción** Haga **clic en** Acción y, a continuación, seleccione la acción que desea realizar para los usuarios seleccionados en los resultados de la búsqueda. Están disponibles las siguientes acciones:

  - **Volver a habilitar para Lync Server** Habilita la cuenta de usuario seleccionada después de que se haya deshabilitado temporalmente.

  - **Deshabilitar temporalmente para Lync Server** Deshabilita la cuenta de usuario en Skype Empresarial Server hasta que vuelva a habilitarla, sin quitar la cuenta de usuario.

  - **Asignar directivas** Abre el [cuadro de diálogo Usuarios:](ms.lync.lscp.UserAssignPolicy.md) Asignar directivas, donde puede configurar las directivas asignadas al usuario.

  - **Ver el estado del PIN** Abre el [cuadro de diálogo Usuarios: Ver](ms.lync.lscp.UserViewPin.md) estado de PIN, que muestra los datos de PIN del usuario seleccionado.

  - **Establecer PIN** Abre el cuadro de diálogo Establecer [PIN,](ms.lync.lscp.UserSetPin.md) donde puede establecer el PIN para el usuario seleccionado.

  - **Bloquear PIN** Bloquea el PIN del usuario.

  - **Desbloquear PIN** Quita el bloqueo del PIN del usuario.

  - **Quitar de Lync Server** Quita la cuenta de usuario de Skype Empresarial Server. El usuario no se elimina de Active Directory.

  - **Quitar certificado de usuario** Quita todos los certificados concedidos al usuario.

  - **Mover usuarios seleccionados al grupo** Abre el [cuadro de diálogo](ms.lync.lscp.UserMove.md) Mover usuario, donde puede seleccionar un grupo al que mover el usuario seleccionado.

  - **Mover todos los usuarios al grupo** Abre el [cuadro de diálogo](ms.lync.lscp.UserMove.md) Mover usuario, donde puede seleccionar un grupo al que mover todos los usuarios seleccionados.


