---
title: Dispositivo de la prueba
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Al agregar un dispositivo, aparece en la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099356"
---
# <a name="test-device"></a>Dispositivo de la prueba

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Al agregar un dispositivo, aparece en la lista de la página **Dispositivo** de prueba del Panel de control de Skype Empresarial Server.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes acciones en la página **Dispositivo de prueba**:

- Agregar un dispositivo de prueba de forma global o para un sitio concreto.

- Modificar las opciones de un dispositivo de prueba existente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Nuevo** Puedes agregar un nuevo dispositivo de prueba con el siguiente ámbito:

  - Global

  - Site

- **Editar** Puedes cambiar las opciones de un dispositivo de prueba en la lista. Al usar esta opción, puede hacer lo siguiente:

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puedes cambiar las opciones de un dispositivo de prueba.

  - **Seleccionar todo** Esta opción selecciona todos los dispositivos de prueba de la lista.

  - **Eliminar** Esta opción elimina todos los dispositivos de prueba seleccionados.

- **Actualizar** Puedes actualizar la lista de dispositivos de prueba para comprobar el estado de las opciones de todos los dispositivos de prueba.

Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) en la documentación de operaciones.
## <a name="see-also"></a>Ver también

[Dispositivo de prueba: Crear nuevo o editar existente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver actualizaciones de software para dispositivos de la organización](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)