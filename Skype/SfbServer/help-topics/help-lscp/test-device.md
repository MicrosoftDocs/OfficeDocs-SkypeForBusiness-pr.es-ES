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
description: Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un único sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.
ms.openlocfilehash: fd32fafd3b334344fe90c28e130e016dfbcf5043
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819050"
---
# <a name="test-device"></a>Dispositivo de la prueba

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un único sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en  la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.

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

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de un dispositivo de prueba.

  - **Seleccionar todo** Esta opción selecciona todos los dispositivos de prueba de la lista.

  - **Eliminar** Esta opción elimina todos los dispositivos de prueba seleccionados.

- **Actualizar** Puedes actualizar la lista de dispositivos de prueba para comprobar el estado de las opciones de todos los dispositivos de prueba.

Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación de operaciones.
## <a name="see-also"></a>Vea también

[Dispositivo de prueba: Crear nuevo o editar existente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver actualizaciones de software para dispositivos de la organización](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
