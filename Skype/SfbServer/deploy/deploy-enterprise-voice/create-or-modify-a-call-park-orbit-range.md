---
title: Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crear o modificar una tabla de rango de órbita llamada Park en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a>Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Skype Empresarial 2015
 
Crear o modificar una tabla de rango de órbita llamada Park en Skype para Business Server Telefonía IP empresarial.
  
Parque de llamada utiliza Órbitas para el estacionamiento de llamadas. Antes de que los usuarios pueden estacionar y recuperar llamadas, debe configurar la tabla de la órbita de llamada Park. Debe especificar los rangos de números de extensión (Órbitas) que su organización se reservará para el estacionamiento de llamadas y defina la ruta para dichos intervalos especificando qué grupo aparcar llamada controla cada rango. A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida; con todo, tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios. Puede crear varios rangos de órbita parque de llamada para cada Skype para grupo Business Server donde está implementada la aplicación llamada Park. Cada rango de órbita parque de llamada debe tener un nombre único global y un único conjunto de extensiones.
  
> [!IMPORTANT]
> Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10 000 órbitas (número máximo) por intervalo y que usted tenga menos de 50 000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez. 
  
Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas. 
  
> [!NOTE]
> No se admite la asignación de números de marcado interno directo (DID) como números orbital en el parque de llamada tabla de órbita. 
  
Use los siguientes procedimientos para crear o modificar un intervalo de órbitas de estacionamiento de llamadas. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Usar Skype para Business Server Control Panel para crear o modificar un rango de números para el estacionamiento de llamadas

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea **Delegar permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.
    
4. En la página **Estacionamiento de llamadas**, siga uno de estos procedimientos:
    
  - Para crear un nuevo intervalo de órbitas, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.
    
    > [!NOTE]
    > Una vez que haya confirmado el intervalo de órbitas para la base de datos, no podrá cambiar este nombre. 
  
  - Para modificar un intervalo de órbitas existente, escriba todo o parte del nombre del intervalo de órbitas en el campo de búsqueda. En la lista de órbitas resultante, haga clic en la órbita que desee, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo de extensiones para esta órbita de estacionamiento de llamadas y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo. Tenga en cuenta:
    
   - El número inicial del intervalo debe ser menor o igual al número final.
    
   - El valor del número inicial del intervalo debe tener la misma longitud que el número final.
    
   - El intervalo de órbitas debe ser único. Este intervalo no se puede superponer con ningún otro.
    
   - Si el intervalo de órbita comienza con el carácter \* o #, el intervalo debe ser mayor que 100.
    
   - Valores válidos: debe coincidir con la cadena de expresión regular ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d {0,8}). Esto significa que el valor debe ser una cadena que comienza con el carácter de cualquier \* o # o un número del 1 al 9 (el primer carácter no puede ser cero). Si el primer carácter es \* o #, el carácter siguiente debe ser un número del 1 al 9 (no puede ser cero). Los caracteres siguientes pueden ser cualquier número del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no es \* o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido por un máximo de ocho caracteres, cada uno un número del 0 al 9 (por ejemplo, "915551212", "41212", "300").
    
   - No debe tener más de 50 000 órbitas por grupo de servidores. Cada intervalo de órbitas normalmente está formado por 100 órbitas o menos, pero puede ser mucho mayor siempre que tenga menos de 10 000 órbitas. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".
    
6. En el **FQDN del servidor de destino**, haga clic en el nombre de dominio completo (FQDN) o identificador del servicio de aplicación que hospeda la aplicación parque de llamada de servicio. Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo de órbitas se enrutarán a este servidor o grupo de servidores.
    
7. Haga clic en **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Usar Skype para negocios de Shell de administración de servidor para crear o modificar un rango de números para el estacionamiento de llamadas

1. Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Utilice **CsCallParkOrbit de nuevo** para crear un nuevo rango de números de la órbita. Utilice **Set CsCallParkOrbit** para modificar un rango existente de números de la órbita.
    
    En la línea de comandos, ejecute:
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Por ejemplo:
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    En el ejemplo siguiente se muestra cómo modificar los números de un intervalos de órbitas existente,
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Vea también

#### 

[Nueva CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Conjunto de CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Eliminar un rango de órbita llamada Park](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

