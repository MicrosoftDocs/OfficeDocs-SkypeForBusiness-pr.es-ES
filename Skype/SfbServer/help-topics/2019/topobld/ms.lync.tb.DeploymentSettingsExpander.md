---
title: Expansor de configuración de implementación
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 'Puede editar las propiedades de una implementación existente con las secciones siguientes:'
ms.openlocfilehash: 2784a1c2f21699a3d5cc30b2fcfba76bf1d3338c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21027243"
---
# <a name="deployment-settings-expander"></a>Expansor de configuración de implementación
 
Puede editar las propiedades de una implementación existente con las secciones siguientes:
  
- Dominio SIP
    
- Direcciones URL simples
    
- Servidor de administración central
    
## <a name="sip-domain"></a>Dominio SIP

Para editar el **Dominio SIP predeterminado**, escriba el nuevo nombre de dominio. 
  
Para agregar **Dominios SIP adicionales admitidos**, escriba el nombre del dominio que quiera agregar. Haga clic en **Agregar** para aceptarlo como nuevo nombre de dominio de Protocolo de inicio de sesión (SIP).
  
Para actualizar un nombre de dominio SIP adicional existente, seleccione el nombre de dominio en cuestión y realice los cambios en el cuadro de texto. Haga clic en **Actualizar** para aceptar el cambio.
  
Para quitar un nombre de dominio SIP adicional definido, seleccione el nombre de dominio y haga clic en **Quitar**.
  
Cuando haya introducido todos los cambios en la página Editar propiedades, haga clic en **Aceptar** para guardar los cambios o en **Cancelar** para descartarlos.
  
## <a name="simple-urls"></a>Direcciones URL simples

Para modificar o definir las direcciones URL simples, necesita decidir cuál de las tres direcciones URL simples es la que desea editar o modificar. Puede elegir entre la dirección URL de acceso telefónico, la dirección URL de la reunión y la dirección URL de acceso administrativo.
  
Para modificar la dirección URL de acceso telefónico o la dirección URL de la reunión, seleccione la dirección URL correspondiente. Haga clic en **Editar URL**. Luego, edite la dirección URL y haga clic en **Aceptar** para guardarla o en **Cancelar** para descartar los cambios.
  
Para agregar una nueva dirección URL, haga clic en **Agregar**. En el cuadro de diálogo **Agregar dirección URL simple**, escriba la dirección URL y haga clic en **Aceptar** para guardarla. Seleccione **Convertir esta dirección en la URL activa para el dominio seleccionado** si quiere configurar la nueva dirección URL como dirección URL activa. Haga clic en **Cancelar** para descartar los cambios.
  
Para convertir una dirección URL distinta en la dirección URL activa (lo que se indica con la marca verde junto a la dirección URL), seleccione la dirección URL y, luego, haga clic en **Establecer como activa**.
  
> [!NOTE]
> Solamente puede haber una dirección URL activa por cada dominio SIP. 
  
Si necesita quitar una dirección URL, selecciónela y haga clic en **Quitar**.
  
> [!CAUTION]
> Lea detenidamente la información que aparece en la página del cuadro de diálogo de configuración de direcciones URL simples. Al quitar una dirección URL de la reunión, es posible que las reuniones programadas por los usuarios queden inaccesibles. Considere la posibilidad de dejar la dirección URL anterior después de convertir la nueva dirección URL en activa. Cuando esté seguro de que los usuarios ya no usan la dirección URL de la reunión antigua, podrá quitarla sin ningún problema. 
  
Para editar o cambiar la dirección URL de acceso administrativo, edite la entrada.
  
Cuando haya introducido todos los cambios en la página Editar propiedades, haga clic en **Aceptar** para guardar los cambios o en **Cancelar** para descartarlos.
  
## <a name="central-management-server"></a>Servidor de administración central

El servidor de administración central se puede cambiar de un grupo de servidores front-end definido a otro. Para cambiar la ubicación del servidor de administración central, seleccione el grupo de servidores front-end de la lista desplegable en **Servidor front-end en el que se instalará el servidor de administración central**. Un servidor front-end puede pertenecer a un grupo de servidores front-end Enterprise Edition o ser un servidor front-end Standard Edition.
  
> [!IMPORTANT]
> Cuando haya definido, publicado e implementado el Almacén de administración central de la infraestructura, ya no podrá cambiarlo de ubicación sin recolocarlo en otro front-end mediante un proceso externo. 
  
Para obtener información detallada acerca de cómo mover el almacén de Administración Central, vea [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) en la referencia del cmdlet de Windows PowerShell.
  

Para obtener información detallada sobre cómo definir y configurar estas opciones, vea [definición y configuración de la topología](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).
  

