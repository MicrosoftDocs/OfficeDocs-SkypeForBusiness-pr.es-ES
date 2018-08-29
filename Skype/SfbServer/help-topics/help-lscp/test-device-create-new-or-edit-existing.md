---
title: Dispositivo de prueba crear nuevos o editar los existentes
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando se agrega un dispositivo, aparece en la lista en la página dispositivo de prueba de la Skype para el Panel de Control de servidor empresarial.
ms.openlocfilehash: 587be60ec730b87a9f7b119dc835fedf4c349802
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246704"
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

Para obtener información detallada acerca de cómo probar dispositivos, vea [Agregar un dispositivo para probar la funcionalidad de actualización](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación sobre operaciones.
## <a name="see-also"></a>Vea también

[Dispositivo de prueba](test-device.md)

[Nuevo-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver actualizaciones de Software para dispositivos de la organización](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)