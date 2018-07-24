---
title: 'Administrar números de acceso telefónico en Skype para Business Server '
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumen: Obtenga información sobre cómo administrar los números de acceso telefónico en Skype para Business Server.'
ms.openlocfilehash: a9e93b52a329a4fdce6817a758b6c6dcb29a0348
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008191"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Administrar números de acceso telefónico en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo administrar los números de acceso telefónico en Skype para Business Server.
  
Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local. 
  
En este tema se describe cómo ver, modificar o eliminar números de acceso a conferencias de acceso telefónico local existentes. Para obtener más información acerca de cómo crear los números de acceso telefónico inicial, vea [Configure telefónico en Skype para Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Ver los números de acceso a conferencias de acceso telefónico local

Puede ver los números de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ver los números de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.
    
4. En la página **Número de acceso telefónico local**, haga clic en el número de acceso que desea ver.
    
5. En **Editar**, active la casilla **Mostrar detalles**.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ver los números de acceso telefónico mediante el uso de Skype para Shell de administración de servidor empresarial

Para ver información sobre los números de acceso telefónico local, use el cmdlet **Get-CsDialInConferencingAccessNumber**.
  
El siguiente comando devuelve una colección de todos los números de acceso telefónico configurados para su uso en la organización: 
  
```
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

Para obtener más información, vea [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificar los números de acceso a conferencias de acceso telefónico local

Puede modificar los números de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificar los números de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.
    
4. En la página **Número de acceso telefónico local**, haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar** y después haga clic en **Mostrar detalles**.
    
    > [!NOTE]
    > Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar. 
  
5. En **Número para mostrar**, escriba el número de teléfono que los usuarios de RTC (Red telefónica conmutada) marcan para unirse a una conferencia. 
    
    Este número se muestra en las invitaciones a reuniones y en la página web Configuración de la conferencia de acceso telefónico local.
    
6. En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico local. Éste es el nombre que está asociado con el número de acceso telefónico de Skype para los resultados de búsqueda empresarial.
    
    Este número se muestra en el cliente cuando un usuario llama al número de acceso. 
    
7. En **URI de línea**, escriba el número E.164 del número de acceso telefónico local en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel.: +14255550200.
    
    > [!NOTE]
    > El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias. 
  
8. En **URI del SIP**, siga este procedimiento:
    
   En el cuadro de texto, escriba un URI del SIP único para este número de acceso a conferencias de acceso telefónico local. Este URI del SIP se muestra en varias ubicaciones, incluidos, pero sin limitarse, para llamar a los mensajes de notificación y las versiones anteriores de clientes de Lync.
    
    > [!NOTE]
    > El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso. 
  
   En el cuadro de lista desplegable, haga clic en el dominio de la aplicación de operador de conferencia que admite el número de acceso telefónico.
    
9. En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico local.
    
    > [!NOTE]
    > Si necesita cambiar el grupo de servidores después de crear el número de acceso, debe usar el cmdlet **Move-CsApplicationEndpoint** o eliminar y volver a crear el número de acceso.
  
10. En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico local. 
    
    El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.
    
11. (Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico local y luego haga clic en **Aceptar**. 
    
    Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.
    
12. Para agregar una región para el número de acceso telefónico, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones que están asociados con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    
13. Para eliminar una región del número de acceso telefónico local, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.
    
14. Haga clic en **Confirmar**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificar los números de acceso telefónico mediante el uso de Skype para Shell de administración de servidor empresarial

Para modificar los números de acceso telefónico local, use el cmdlet **Set-CsDialInConferencingAccessNumber**.
  
El siguiente comando modifica la propiedad DisplayName para el número de acceso a conferencia de acceso telefónico local con el valor Identity sip:RedmondDialIn@litwareinc.com. En este ejemplo, el nombre para mostrar se establece como "Redmond Dial-In Access Number":
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

En el siguiente ejemplo, el número de acceso a conferencia de acceso telefónico local con el valor Identity sip:RedmondDialIn@litwareinc.com se modifica para incluir dos regiones: Redmond y Seattle. Para ello, se llama al parámetro Regions, seguido de las dos regiones (dos valores de cadena separados por comas). Tenga en cuenta que este comando producirá un error a menos que las regiones de Redmond y Seattle ya se hayan definido en planes de marcado.
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Para obtener más información, vea [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Eliminar un número de acceso a conferencias de acceso telefónico local

Puede eliminar un número de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Eliminar un número de acceso telefónico mediante Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.
    
4. En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y luego en **Eliminar**.
    
5. Haga clic en **Aceptar**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Eliminar un número de acceso telefónico mediante Skype para Shell de administración de servidor empresarial

Para eliminar un número de acceso a conferencias de acceso telefónico local, use el comando **Remove-Cs DialInConferencingAccessNumber**.
  
El siguiente comando elimina el número de acceso a conferencias de acceso telefónico local con el valor Identity sip:RedmondDialInAccess@litwareinc.com:
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local asociados a la región noroeste:
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local en los que el italiano es el idioma principal:
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Para obtener más información, consulte [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

