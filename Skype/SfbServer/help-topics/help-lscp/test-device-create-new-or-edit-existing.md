---
title: Probar dispositivo Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de pruebas a la página Dispositivo de prueba y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Al agregar un dispositivo, aparece en la lista de la página Probar dispositivo del panel de control Skype Empresarial Server control.
ms.openlocfilehash: 5f45b9297da4501f4bf92d0452b25c88564b5ed2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841492"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo de la prueba: Crear nuevos o editar los existentes

La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de pruebas a la página **Dispositivo de prueba** y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agregas un dispositivo, aparece en la lista de la página **Dispositivo de** prueba del panel de control Skype Empresarial Server prueba.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba**:

- Agregar un nuevo dispositivo de prueba.

- Modificar las propiedades de un dispositivo de prueba existente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (Global o Site) del dispositivo de prueba.

- **Nombre** Puedes agregar o modificar el nombre del dispositivo de prueba.

- **Nombre del dispositivo** Puedes agregar o modificar el nombre del dispositivo de prueba.

- **Tipo de identificador** Puedes seleccionar el método que quieres usar para identificar el dispositivo seleccionando una de las siguientes opciones:

  - **Dirección MAC**

  - **Número de serie**

- **Identificador único** Puedes escribir la dirección MAC o el número de serie del dispositivo.

Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) en la documentación de operaciones.
## <a name="see-also"></a>Consulte también

[Dispositivo de la prueba](test-device.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver actualizaciones de software para dispositivos de la organización](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)