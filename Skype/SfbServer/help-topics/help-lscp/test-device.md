---
title: Dispositivo de la prueba
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista de la página probar dispositivo del panel de control de Skype empresarial Server.
ms.openlocfilehash: f60cf047c1a6ecf902283920de9513e1a51c1acc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685763"
---
# <a name="test-device"></a>Dispositivo de la prueba

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista de la página **probar dispositivo** del panel de control de Skype empresarial Server.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **probar dispositivo** :

- Agregar un dispositivo de prueba globalmente o para un sitio en particular.

- Modificar las opciones de un dispositivo de prueba existente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Nuevo** Puede Agregar un nuevo dispositivo de prueba con el siguiente ámbito:

  - Global

  - Sitio

- **Editar** Puede cambiar las opciones de un dispositivo de prueba en la lista. Al usar esta opción, puede hacer lo siguiente:

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para un dispositivo de prueba.

  - **Seleccionar todo** Esta opción selecciona todos los dispositivos de prueba de la lista.

  - **Eliminar** Esta opción elimina todos los dispositivos de prueba seleccionados.

- **Actualizar** Puede actualizar la lista de dispositivos de prueba para comprobar el estado de las opciones de todos los dispositivos de prueba.

Para más detalles sobre cómo probar dispositivos, mire [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación de operaciones.
## <a name="see-also"></a>Vea también

[Dispositivo de prueba: Crear nuevo o editar existente](test-device-create-new-or-edit-existing.md)

[Nuevo: CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Ver las actualizaciones de software de los dispositivos de su organización](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
