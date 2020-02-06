---
title: Número de teléfono sin asignar crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792168"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de teléfono sin asignar: Crear nuevos o editar los existentes

> [!NOTE]
> La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar la 2019 de Skype empresarial con Exchange 2013 o Exchange 2016. Debido a cambios en el soporte técnico de Exchange 2019, la integración de mensajería unificada de Exchange se subraya en favor del buzón de voz de nube y las características del operador automático de la nube.

Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.

> [!IMPORTANT]
> Cuando haya terminado de crear un intervalo de números nuevo sin asignar o de editar uno existente, haga clic en **Aceptar** para volver a la página **número sin asignar** que muestra todos los intervalos de números. Los cambios realizados en la página **nuevo rango de números sin asignar** o en la página **Editar número sin asignar** no se guardan en la base de datos hasta que haga clic en **confirmar todo** en la página **número sin asignar** .

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifique el intervalo de números sin asignar. Después de guardar el rango, este nombre no se puede cambiar.

- **Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números sin asignar. En el segundo campo, escriba el número final del intervalo.

  - El número inicial del intervalo debe ser menor o igual al número final.

  - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.

  - El número debe coincidir con la expresión regular (Tel:)? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. Esto significa que el número puede comenzar con la cadena Tel: (si no especifica esa cadena se agregará automáticamente), un signo más (+) y un dígito de 1 a 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".

- **Servicio de anuncios** Seleccione **anuncio** para que la aplicación de anuncios controle la llamada entrante o la **mensajería unificada de Exchange** para que un operador automático de mensajería unificada de Exchange controle la llamada entrante.

- Si ha seleccionado **anuncio** para el **servicio de anuncios**:

  - **FQDN del servidor de destino** Seleccione el identificador de servicio del servicio de aplicación que ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este rango de números no asignados.

  - **Anuncio** Seleccione el anuncio que se va a reproducir para este rango de números no asignados.

- Si seleccionaste **mensajería unificada de Exchange** para el **servicio de anuncios**:

  - **Número de teléfono del operador automático** Seleccione el número de teléfono para el operador automático de MU de Exchange.

Para obtener más información sobre las características y capacidades del anuncio, consulte [planear la aplicación de anuncios en Skype empresarial](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación. Para más detalles sobre cómo trabajar con intervalos de números sin asignar, mire [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.


