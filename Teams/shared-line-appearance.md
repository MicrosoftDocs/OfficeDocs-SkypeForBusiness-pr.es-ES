---
title: Apariencia de línea compartida en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Apariencia de línea compartida permite a los usuarios elegir un delegado para responder o administrar las llamadas en su nombre.
ms.openlocfilehash: 41c0eb9f740a7fa771769159fe4f560019293857
ms.sourcegitcommit: f69b5dbdbd61f77ffc0494886516effe35a0c338
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2018
ms.locfileid: "27283763"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Apariencia de línea compartida en Microsoft Teams

Apariencia de línea compartida es parte de la característica de delegación que permite a los usuarios elegir un delegado para responder o administrar las llamadas en su nombre. Esta característica es útil si un usuario tiene un auxiliar administrativo que con regularidad administra las llamadas del usuario. En el contexto de la apariencia de línea compartida, un administrador es alguien que autoriza a un delegado para realizar o recibir llamadas en su nombre, y un delegado puede realizar y recibir llamadas en nombre de otra persona.

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación sólo de los equipos. Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Se requiere una licencia

Un usuario debe ser un usuario de enterprise voice a ser un delegado o configurar la delegación y permitir que otros usuarios realicen y reciban llamadas en su nombre.

Los administradores y delegados deben enterprise voice está habilitado. La experiencia de línea compartida forma parte de la delegación y no requiere ninguna licencia adicional. Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configuración de la delegación y la apariencia de línea compartida

Delegación y la apariencia de línea compartidos son las características de controlado por el usuario: no hay ninguna configuración de administración para configurar. Para obtener información acerca de cómo usar la característica, vea el [recurso compartido de una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

## <a name="shared-line-appearance-feature-availability"></a>Compartir la disponibilidad de características de apariencia de línea

Apariencia de línea compartidos actualmente es compatible con las siguientes aplicaciones y dispositivos.

| Capacidad | Escritorio de los equipos | Aplicación de Mac de los equipos | Los equipos Web App (borde) |Los equipos móviles iOS y Android aplicación | Teléfono IP de los equipos |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar la delegación | Sí | Sí | Sí | No | No |
| Recibir llamadas en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un número de teléfono en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un usuario de los equipos en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Ver la vista de administración de líneas compartidas | Sí | Sí | Sí | No | No |
| Vea la vista de administración de actividades de llamada del director | Sí | Sí | Sí | No | No |
| Vea la vista del Administrador de delegados | Sí | Sí | Sí | No | No |
| Administrador o administrador puede en espera o reanudarla | Sí | Sí | Sí | No | No |

## <a name="limitations"></a>Limitaciones

Los administradores pueden agregar hasta 25 delegados y los delegados pueden tener administradores de hasta 25. No hay ningún límite para el número de relaciones de delegación que se pueden crear en un inquilino. 
 
Si el usuario delegado y el delegado no están en la misma ubicación geográfica, es responsabilidad del proveedor de RTC para permitir que el identificador de autor de la llamada mostrar la copia de seguridad desde una ubicación geográfica diferente para una llamada de delegado (en nombre de). 
 
## <a name="more-information"></a>Más información

[Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
