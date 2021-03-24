---
title: 'Administrar números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Summary: Learn how to manage dial-in conferencing access numbers in Skype for Business Server.'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099156"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Administrar números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar los números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server.
  
Al implementar conferencias de acceso telefónico local, debe configurar los números de teléfono que los usuarios pueden marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico local aparecen en las invitaciones a reuniones y en la página web Configuración de conferencia de acceso telefónico local. 
  
En este tema se describe cómo ver, modificar o eliminar números de acceso a conferencias de acceso telefónico local existentes. Para obtener más información acerca de cómo crear números de acceso telefónico local iniciales, vea [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Ver números de acceso a conferencias de acceso telefónico local

Puede ver los números de acceso a conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ver números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.
    
4. En la página **Número de acceso telefónico**, haga clic en el número de acceso que desea ver.
    
5. En **Editar**, active la **casilla Mostrar** detalles.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ver números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server

Para ver información sobre los números de acceso telefónico local, use el cmdlet **Get-CsDialInConferencingAccessNumber.**
  
El siguiente comando devuelve una colección de todos los números de acceso a conferencias de acceso telefónico local configurados para su uso en la organización: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

A continuación se muestra un ejemplo del tipo de información devuelta:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificar números de acceso a conferencias de acceso telefónico local

Puede modificar los números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificar los números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.
    
4. En la **página Número de acceso telefónico,** haga clic en uno de los números de acceso telefónico en la lista, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles.**
    
    > [!NOTE]
    > El uso del campo de búsqueda para buscar el contenido de una columna en la lista de números de acceso telefónico no puede producir los resultados esperados. En su lugar, ordena la lista por la columna de interés para identificar el número de acceso telefónico que quieres ver o cambiar. 
  
5. En **Número de pantalla**, escriba el número de teléfono que los usuarios telefónicos de la red telefónica conmutada (RTC) marcan para unirse a una conferencia. 
    
    Este número se muestra en invitaciones a reuniones y en la página web Configuración de conferencia de acceso telefónico local.
    
6. En **Nombre para mostrar,** escriba una descripción para el número de acceso telefónico. Este es el nombre asociado al número de acceso telefónico en los resultados de búsqueda de Skype Empresarial.
    
    Este nombre se muestra en el cliente cuando un usuario llama al número de acceso. 
    
7. En **URI** de línea , escriba el número E.164 del número de acceso telefónico en formato URI de TEL, incluido el símbolo + antes del número y excluyendo espacios. Por ejemplo, tel:+14255550200.
    
    > [!NOTE]
    > Otro número de acceso de conferencia de acceso telefónico local no puede reutilizar el mismo URI de línea. 
  
8. En **URI de SIP,** haga lo siguiente:
    
   En el cuadro de texto, escriba un URI SIP único para este número de acceso de conferencia de acceso telefónico local. Este URI de SIP se muestra en varias ubicaciones, incluidos, entre otros, los mensajes de notificación de llamadas y las versiones anteriores de los clientes de Lync.
    
    > [!NOTE]
    > Otro número de acceso de conferencia de acceso telefónico local no puede reutilizar el mismo URI de SIP. El URI de SIP no se puede modificar después de crear el número de acceso. La única forma de cambiar el URI de SIP es eliminar y volver a crear el número de acceso. 
  
   En el cuadro de lista desplegable, haga clic en el dominio de la aplicación operador de conferencia que admite este número de acceso telefónico local.
    
9. En **Grupo** de servidores, haga clic en el grupo que ejecuta la instancia de Operador de conferencia que admite este número de acceso telefónico local.
    
    > [!NOTE]
    > Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet **Move-CsApplicationEndpoint** o eliminar y volver a crear el número de acceso.
  
10. En **Idioma principal,** haga clic en el idioma en el que se reproducen los mensajes de este número de acceso telefónico local. 
    
    El idioma principal es el idioma que usa el operador de conferencia para responder a la llamada. Los idiomas admitidos se muestran junto con cada número de teléfono de acceso en la página web Configuración de conferencia de acceso telefónico local.
    
11. (Opcional) En **Idiomas** secundarios (máximo de cuatro), haga clic en Agregar **,** seleccione uno o más idiomas adicionales que desee admitir para los autores de llamadas a este número de acceso telefónico local y, a continuación, haga clic en **Aceptar**. 
    
    Puede elegir hasta cuatro idiomas secundarios para cada número de acceso telefónico local. Los usuarios pueden seleccionar un idioma secundario antes de escribir el identificador de conferencia cuando llamen a una conferencia.
    
12. Para agregar una región para el número de acceso telefónico, en Regiones **asociadas,** haga clic en Agregar **,** haga clic en una o más regiones asociadas con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    
13. Para eliminar una región del número de acceso telefónico, en Regiones **asociadas,** haga clic en la región que desea eliminar y, a continuación, haga clic en **Quitar**.
    
14. Haga clic en **Confirmar**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificar los números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server

Para modificar los números de acceso telefónico local, use el cmdlet **Set-CsDialInConferencingAccessNumber.**
  
El siguiente comando modifica la propiedad DisplayName para el número de acceso de conferencia de acceso telefónico local con la propiedad Identity sip:RedmondDialIn@litwareinc.com. En este ejemplo, el nombre para mostrar se establece en "Redmond Dial-In Access Number":
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

En el siguiente ejemplo, se modifica el número de acceso a conferencias de acceso telefónico local con el objeto Identity sip:RedmondDialIn@litwareinc.com para incluir dos regiones: Redmond y Seattle. Para ello, se llama al parámetro Regions, seguido de las dos regiones (dos valores de cadena separados por comas). Tenga en cuenta que este comando producirá un error a menos que las regiones de Redmond y Seattle ya se hayan definido en planes de marcado.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Para obtener más información, [vea Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Eliminar un número de acceso de conferencia de acceso telefónico local

Puede eliminar un número de acceso a conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Eliminar un número de acceso a conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.
    
4. En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y, a continuación, en **Eliminar**.
    
5. Haga clic en **Aceptar**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Eliminar un número de acceso a conferencias de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server

Para eliminar un número de acceso a conferencias de acceso telefónico local, use **remove-CsDialInConferencingAccessNumber**.
  
El siguiente comando elimina el número de acceso de conferencia de acceso telefónico local con identity sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local asociados con la región Noroeste:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local donde el italiano es el idioma principal:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Para obtener más información, [vea Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
