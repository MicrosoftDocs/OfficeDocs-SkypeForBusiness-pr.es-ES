---
title: Número de teléfono sinsignado Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 49837269f81eaee09a0c191008234345d1d6d19f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097056"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de teléfono sin asignar: Crear nuevos o editar los existentes

> [!NOTE]
> La mensajería unificada de Exchange permanece disponible en Skype Empresarial Server 2019 al integrar Skype Empresarial 2019 con Exchange 2013 o Exchange 2016. Debido a los cambios en la compatibilidad con Exchange 2019, la integración de mensajería unificada de Exchange se está desmarcando a favor del correo de voz en la nube y las características Operador automático nube.

Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.

> [!IMPORTANT]
> Cuando termine de crear un nuevo intervalo numérico sin asignar o de editar uno existente, haga clic en **Aceptar** para volver a la página **Número no asignado**, que muestra todos los intervalos numéricos. Los cambios que realice en la página **Nuevo intervalo numérico sin asignar** o en la página **Editar intervalo numérico sin asignar** no se confirman en la base de datos hasta que no haga clic en **Confirmar todo** en la página **Número no asignado**.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifique el intervalo de números sin signo. Una vez que guarde el intervalo, el nombre no se podrá cambiar.

- **Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números sin signo. En el segundo campo, escriba el número de finalización del intervalo.

  - El número inicial del intervalo debe ser menor o igual al número final del intervalo.

  - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.

  - El número debe coincidir con la expresión regular ( `tel:` )?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. Esto significa que el número puede comenzar con la cadena 'tel:'. Si no especifica esa cadena, se agregará automáticamente, como un signo más (+) y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".

- **Servicio de anuncios** Seleccione **Anuncio** para que la aplicación Anuncio controle la llamada entrante o la mensajería unificada de **Exchange** para que una mensajería unificada de Exchange Operador automático la llamada entrante.

- Si ha seleccionado **Anuncio** para el servicio **Anuncio**:

  - **FQDN del servidor de destino** Seleccione el identificador de servicio del servicio de aplicación que ejecuta la aplicación Anuncio que controlará las llamadas entrantes a este rango de números sinsignación.

  - **Anuncio** Seleccione el anuncio que se va a reproducir para este intervalo de números sin signo.

- Si ha seleccionado **Mensajería unificada de Exchange** para el servicio **Anuncio**:

  - **Operador automático de teléfono** Seleccione el número de teléfono para la mensajería unificada de Exchange Operador automático.

Para obtener más información sobre las características y capacidades del anuncio, vea [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación sobre planeación. Para obtener más detalles sobre cómo trabajar con rangos de números sin asignar, vea [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) en la documentación de operaciones.