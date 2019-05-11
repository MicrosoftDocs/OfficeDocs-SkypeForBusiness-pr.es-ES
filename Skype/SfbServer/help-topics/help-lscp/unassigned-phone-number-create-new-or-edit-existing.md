---
title: Número de teléfono sin asignar crear nuevos o editar los existentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 46660d5d1e873dfb5da5cb6643a0b654942dcd6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929521"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de teléfono sin asignar: Crear nuevos o editar los existentes

Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.

> [!IMPORTANT]
> Cuando haya terminado de crear un nuevo intervalo numérico sin asignar o modificar uno existente, haga clic en **Aceptar** para volver a la página **Número sin asignar** que se enumera todos los intervalos de números. Los cambios realizados en la página **Nuevo Unassigned Number Range** o en la página **Editar Rage de número sin asignar** no se confirman en la base de datos hasta que haga clic en **Confirmar todo** en la página **Número sin asignar** .

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifica el intervalo de números sin asignar. Después de guardar el intervalo, no se puede cambiar este nombre.

- **Intervalo de número** En el primer campo, escriba el número inicial del intervalo numérico sin asignar. En el segundo campo, escriba el número final del rango.

  - El número inicial del intervalo debe ser menor o igual al número final.

  - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.

  - El número debe coincidir con la expresión regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?. Esto significa que el número de puede comenzar con la cadena tel: (si no se especifica esa cadena se agregará automáticamente para usted), un signo más (+) y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".

- **Servicio de anuncio** Seleccione el **anuncio** para que la aplicación de anuncio controlar la llamada entrante o **Mensajería unificada de Exchange** para tener un operador de Exchange UM automático controlar la llamada entrante.

- Si ha seleccionado **anuncio** para **el servicio de anuncio**:

  - **FQDN del servidor de destino** Seleccione el identificador de servicio de la aplicación que se ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números sin asignar.

  - **Anuncio** Seleccione el anuncio se reproducirá para este intervalo de números sin asignar.

- Si ha seleccionado **Mensajería unificada de Exchange** para **el servicio de anuncio**:

  - **Número de teléfono del operador automático** Seleccione el número de teléfono para el operador de Exchange UM automático.

Para obtener información detallada sobre las capacidades y características de anuncio, consulte [Plan para la aplicación de anuncio en Skype para 2015 empresarial](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación. Para más detalles sobre cómo trabajar con intervalos de números sin asignar, mire [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.


