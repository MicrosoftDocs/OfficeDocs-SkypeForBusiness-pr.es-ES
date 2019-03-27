---
title: Dispositivo de prueba crear nuevos o editar los existentes
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando se agrega un dispositivo, aparece en la lista en la página dispositivo de prueba de la Skype para el Panel de Control de servidor empresarial.
ms.openlocfilehash: 1bb61f99ceab29eb3915e7650e1a760b1798f0db
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882274"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo de prueba: Crear nuevo o editar existente

La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando se agrega un dispositivo, aparece en la lista en la página **Dispositivo de prueba** de la Skype para el Panel de Control de servidor empresarial.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba** puede realizar las siguientes tareas:

- Agregar un nuevo dispositivo de prueba.

- Modificar las propiedades de un dispositivo de prueba existente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (Global o sitio) del dispositivo de prueba.

- **Nombre** Puede agregar o modificar el nombre del dispositivo de prueba.

- **Nombre de dispositivo** Puede agregar o modificar el nombre del dispositivo de prueba.

- **Tipo de identificador** Puede seleccionar el método que usar para identificar el dispositivo seleccionando una de las siguientes opciones:

  - **Dirección MAC**

  - **Número de serie**

- **Identificador único** Puede escribir la dirección MAC o número de serie del dispositivo.

Para más detalles sobre cómo probar dispositivos, mire [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación de operaciones.
## <a name="see-also"></a>Consulte también

[Dispositivo de la prueba](ms.lync.lscp.ClientDeviceTestMain.md)

[Nuevo-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver actualizaciones de Software para dispositivos de la organización](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
