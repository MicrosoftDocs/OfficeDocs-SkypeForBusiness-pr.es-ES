---
title: Estacionamiento y recuperación en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/17/2018
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
description: Use estacionamiento y recuperación para realizar una llamada en espera en el servicio de los equipos en la nube.
ms.openlocfilehash: 004a5b12e178a6460ef05f7c6f5c5738c8ced042
ms.sourcegitcommit: 0e671e6e6fdd25227068c7e3a3a5509b6536d2b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2018
ms.locfileid: "27294191"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación en Microsoft Teams

Estacionamiento y recuperación es una característica que permite a un usuario realizar una llamada en espera en el servicio de los equipos en la nube. Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionar la llamada o a otro usuario, a continuación, puede utilizar ese código y aplicaciones compatibles o dispositivo para recuperar la llamada. 

Algunos de los escenarios comunes para el uso de estacionamiento de llamadas son: 

- Un recepcionista aparca una llamada de alguien que trabaje en una fábrica. La recepcionista anuncia a continuación, la llamada y el número de código a través del sistema de dirección pública. El usuario que la llamada es para, a continuación, puede elegir un teléfono de los equipos en la fábrica y escriba el código para recuperar la llamada.
- Un usuario aparca una llamada en un dispositivo móvil debido a que la batería del dispositivo se está quedando sin energía. El usuario puede, a continuación, escriba, a continuación, el código para recuperar la llamada desde un teléfono de escritorio de los equipos.
- Un parques representante de soporte técnico un cliente de llamadas y envía un anuncio en un canal de los equipos de con un experto recuperar la llamada y ayudar al cliente. Con un experto entra en el código en los clientes de equipos para recuperar la llamada

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación sólo de los equipos. Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Se requiere una licencia

Para estacionar y recuperar las llamadas, un usuario debe ser un usuario de Enterprise Voice y un administrador debe conceder al usuario una directiva de estacionamiento de llamada. Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Estacionamiento y recuperación de disponibilidad de la característica

Estacionamiento y recuperación es compatible actualmente con los siguientes clientes y dispositivos. (Admite en el modo de sólo los equipos, con o sin conectividad RTC).

| Capacidad | Escritorio de los equipos | Aplicación de Mac de los equipos | Los equipos Web App (borde) |Los equipos móviles iOS y Android aplicación | Teléfono IP de los equipos | Skype para teléfono IP empresarial |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Estacionar una llamada | Sí | Sí | Sí | Próximamente | Próximamente| No |
| Recuperar una llamada estacionada | Sí | Sí | Sí | Próximamente | Próximamente| No |
| Timbre de llamada reactivar recuperado atrás | Sí | Sí | Sí | Próximamente | Próximamente| No |

## <a name="configuring-call-park-and-retrieve"></a>Configuración de estacionamiento y recuperación

Debe ser un administrador para configurar estacionamiento y recuperación, y la característica está deshabilitada de forma predeterminada. Puede habilitar para los usuarios y crear grupos de usuarios mediante la directiva de estacionamiento de llamada. Cuando se aplica la misma directiva a un conjunto de usuarios, podrán estacionar y recuperar las llamadas entre sí. Para configurar el estacionamiento de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamada, siga el procedimiento siguiente.

Para obtener información acerca de cómo usar el estacionamiento de llamadas y recuperar característica, vea [estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurar el estacionamiento de llamadas y recuperar con PowerShell

Use el cmdlet de PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) para crear una directiva de estacionamiento de llamada.

Use el cmdlet de PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) para conceder una directiva de estacionamiento de llamada.

Puede cambiar la configuración predeterminada mediante el uso [Conjunto CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) como se indica a continuación:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Solución de problemas

Si los usuarios no pueden ver el estacionamiento de o recuperar botón: 

- Compruebe que el usuario tiene la directiva de estacionamiento de llamadas habilitada. 

Si un usuario intenta recuperar una llamada y no tiene éxito, compruebe lo siguiente:

- Compruebe que el usuario está utilizando el cliente de los equipos o un teléfono o dispositivo habilitado para los equipos
- ¿Agrupación: es el usuario miembro del grupo de estacionamiento de llamada?
- Modo de isla – estacionamiento y recuperación no está disponible en el modo de la isla de los equipos.
- La llamada ya se ha recuperado o terminada.

## <a name="more-information"></a>Más información

[Estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).