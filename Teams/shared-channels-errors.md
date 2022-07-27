---
title: Errores de canales compartidos en Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Obtenga información sobre cómo corregir errores en canales compartidos en Microsoft Teams.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024191"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Errores de canales compartidos en Microsoft Teams

Si los usuarios ven mensajes de error al intentar agregar a usuarios externos a la organización a canales compartidos, consulte la configuración de este artículo. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>Debido a la directiva de administración, no puede agregar personas externas al canal. Para obtener más información, habla con el administrador.

Teams usa Grupos de Microsoft 365 para la pertenencia a equipos. La configuración de invitado Grupos de Microsoft 365 debe estar activada para que los usuarios externos a la organización se agreguen a un canal compartido. Si los usuarios ven este error, compruebe la configuración de Grupos de Microsoft 365 para las personas de fuera de la organización.

Para establecer la configuración de Grupos de Microsoft 365 para personas de fuera de la organización
1. En la Centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **Configuración**.
1. Haga clic en **Configuración de la organización**.
1. En la lista, haga clic en **Grupos de Microsoft 365**.
1. Asegúrese de que las **casillas Permitir que los propietarios del grupo agreguen personas de fuera de la organización para Grupos de Microsoft 365 como invitados** y las casillas **Permitir que los miembros del grupo invitado accedan al contenido del grupo** están activadas.
1. Si ha realizado cambios, haga clic en **Guardar cambios**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>Debido a la directiva de administración, no puede agregar personas externas al canal

Las directivas de canales de Teams determinan cómo pueden interactuar los usuarios con los canales compartidos. Si los usuarios ven este mensaje de error, compruebe la directiva de canal de ese usuario.

Para establecer la directiva para invitar a personas de fuera de la organización a canales compartidos
1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Teams > Directivas de Teams.
1. Seleccione la directiva a la que está asignado el usuario.
1. Asegúrese de que **La opción Invitar a usuarios externos a canales compartidos** está **activada**.
1. Si has realizado cambios, selecciona **Aplicar**.

Para obtener más información sobre las directivas de canales de Teams, vea [Administrar directivas de canal en Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>No puede compartir este canal con personas de esta organización

Si los usuarios ven este error, se les impide compartir el canal con personas de la otra organización mediante la configuración de acceso entre espacios empresariales de Azure Active Directory. Esto puede deberse a la configuración de entrada de su organización o a la configuración de salida de la otra organización.

Para comprobar la configuración de entrada de su organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, después, seleccione **Configuración de acceso entre espacios empresariales**.
1. Seleccione el vínculo de acceso de entrada de la organización que desea comprobar.
1. En la pestaña **Conexión directa B2B** , elige **Personalizar configuración**.
1. En la pestaña **Usuarios y grupos** externos, asegúrese de que **permitir el acceso** y **Todos los usuarios y grupos externos** están seleccionados, o si ha elegido **Seleccionar usuarios y grupos externos**, asegúrese de que el usuario al que se invita es un miembro de los grupos seleccionados.
1. Si ha realizado cambios, seleccione **Guardar** y cierre la hoja **Configuración de acceso entrante** .

Si los usuarios siguen viendo el error, compruebe con la organización con la que están colaborando. La configuración de salida de la organización puede no permitir el uso compartido con su organización. Para obtener información sobre cómo configurar canales compartidos entre organizaciones, vea [Colaborar con participantes externos en un canal compartido](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>No hemos podido encontrar ninguna coincidencia. Asegúrese de que la dirección de correo electrónico es correcta o hable con su administrador

Si los usuarios ven este error, Microsoft 365 no puede encontrar la dirección de correo electrónico especificada en la organización externa. Tendrá que confirmar la dirección con la organización externa.

