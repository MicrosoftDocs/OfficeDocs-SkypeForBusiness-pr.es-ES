---
title: Expansor de configuración de implementación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede editar las propiedades de una implementación existente con las secciones siguientes:'
ms.openlocfilehash: 4eab2f0d6468e62c550476717a7af433315b0728
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811160"
---
# <a name="deployment-settings-expander"></a>Expansor de configuración de implementación

Puede editar las propiedades de una implementación existente con las secciones siguientes:

- Dominio SIP

- Direcciones URL simples

- Servidor de administración central

## <a name="sip-domain"></a>Dominio SIP

Para editar el **Dominio SIP predeterminado**, escriba el nuevo nombre de dominio.

Para agregar **Dominios SIP adicionales admitidos**, escriba el nombre del dominio que desea añadir. Haga clic en **Agregar** para aceptarlo como nuevo nombre de dominio del protocolo de inicio de sesión (SIP).

Para actualizar un nombre de dominio SIP adicional existente, seleccione el nombre de dominio y realice los cambios en el cuadro de texto. Haga clic en **Actualizar** para aceptar el cambio.

Para quitar un nombre de dominio SIP adicional definido, seleccione el nombre de dominio y, a continuación, haga clic en **Quitar**.

Cuando haya terminado de introducir los cambios en la página Editar propiedades, haga clic en **Aceptar** para guardarlos. Haga clic en **Cancelar** para descartarlos.

## <a name="simple-urls"></a>Direcciones URL simples

Para modificar o definir las direcciones URL simples, debe decidir cuál de las tres direcciones URL simples es la que desea editar o modificar. Puede elegir entre la dirección URL de acceso telefónico, la dirección URL de la reunión y la dirección URL de acceso administrativo.

Para modificar la dirección URL de acceso telefónico o la dirección URL de la reunión, seleccione la dirección URL que quiere cambiar. Haga clic en **Editar dirección URL**. A continuación, edite la dirección URL y haga clic en **Aceptar** para guardarla. Haga clic en **Cancelar** si desea descartar los cambios.

Para agregar una nueva dirección URL, haga clic en **Agregar**. En el cuadro de diálogo **Agregar dirección URL simple**, especifique la dirección URL y haga clic en **Aceptar** para guardarla. Seleccione **Convertir esta dirección URL en activa para el dominio seleccionado** si desea configurar la nueva dirección URL como dirección URL activa. Haga clic en **Cancelar** para descartar los cambios.

Para convertir una dirección URL distinta en la dirección URL activa (lo que se indica con la marca verde junto a la dirección URL), seleccione la dirección URL y, a continuación, haga clic en **Convertir en activa**.

> [!NOTE]
> Solamente puede haber una dirección URL activa para cada dominio SIP.

Si desea quitar una dirección URL, selecciónela y haga clic en **Quitar**.

> [!CAUTION]
> Lea detenidamente la información que aparece en la página de diálogo de configuración de direcciones URL simples. Al quitar una dirección URL de la reunión es posible que las reuniones programadas por los usuarios queden inaccesibles. Considere la posibilidad de dejar la dirección URL anterior después de convertir la nueva dirección URL en activa. Cuando esté seguro que los usuarios ya no utilizan la dirección URL de la reunión antigua podrá quitarla sin ningún problema.

Para editar o cambiar la dirección URL de acceso administrativo, edite la entrada.

Cuando haya introducido todos los cambios en la página Editar propiedades, haga clic en **Aceptar** para guardar los cambios. Haga clic en **Cancelar** para descartar los cambios.

## <a name="central-management-server"></a>Servidor de administración central

El servidor de administración central se puede cambiar de un grupo de servidores front-end definido a otro. Para cambiar la ubicación del servidor de administración central, seleccione el grupo de servidores front-end de la lista desplegable en **Servidor front-end al que instalar el servidor de administración central**. Un servidor front-end puede ser un grupo de servidores front-end Enterprise Edition o de uno Standard Edition.

> [!IMPORTANT]
> Cuando haya definido, publicado e implementado el almacén de administración central de la infraestructura ya no podrá cambiarlo de ubicación sin recolocarlo a otro front-end mediante un proceso externo.

Para obtener más información sobre cómo mover el almacén de administración central, consulte [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) en la referencia Windows PowerShell cmdlet.


Para más información sobre cómo definir y configurar estas opciones, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).


