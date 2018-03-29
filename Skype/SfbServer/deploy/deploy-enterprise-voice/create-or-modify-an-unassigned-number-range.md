---
title: Crear o modificar un intervalo numérico sin asignar en Skype Empresarial Server 2015
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Crear, modificar o eliminar sin asignar intervalos numéricos para aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server. Esto afecta a cómo se administran las llamadas a números sin asignar.
ms.openlocfilehash: e4a62072eeffd1cfe8d1cb81fceeb4e52cc68199
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server-2015"></a>Crear o modificar un intervalo numérico sin asignar en Skype Empresarial Server 2015
 
Crear, modificar o eliminar sin asignar intervalos numéricos para aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server. Esto afecta a cómo se administran las llamadas a números sin asignar.
  
Skype para Business Server le permite decir lo que ocurre con las llamadas entrantes a los números que son válidas para su organización, pero que no estén asignados a un usuario o un teléfono. Para administrar las llamadas de este tipo, deberá configurar una tabla de números no asignados. Puede utilizar la tabla para enrutar las llamadas a una aplicación de anuncio o en un servidor de mensajería unificada de Exchange.
  
La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.
  
## <a name="configure-unassigned-phone-numbers"></a>Configuración de números de teléfono sin asignar

Utilice uno de los siguientes procedimientos para configurar intervalos de números no asignados para la aplicación de anuncio.
  
> [!IMPORTANT]
> Antes de configurar la tabla de números sin asignar, el sistema debe ya anuncios definidos o bien configurar un Operador automático de Exchange Unified Messaging (UM). 
  
> [!TIP]
> Cuando alguien llama a un número sin asignar, Skype para Business Server busca la tabla sin asignar número de arriba a abajo y utiliza el primer rango coincidente. Por consiguiente, si quiere que se lleve a cabo una acción determinada como último recurso, deberá especificarla para el último intervalo en la tabla. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Usar Skype para Business Server Control Panel para configurar números de teléfono sin asignar

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea **Delegar permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.
    
4. En la página **Número sin asignar**, siga uno de estos procedimientos:
    
   - Para crear un nuevo intervalo de números, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.
    
    > [!NOTE]
    > Una vez que haya confirmado el nuevo intervalo de números sin asignar para la base de datos, no podrá cambiar este nombre. 
  
   - Para modificar un intervalo de números existente, escriba en el campo de búsqueda todo el intervalo de números o parte de él. En la lista de intervalos numéricos resultante, haga clic en el nombre que desee, en **Editar** y, por último, en **Mostrar detalles**.
    
5. En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.
    
   - El número inicial del intervalo debe ser menor o igual al número final.
    
   - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.
    
   - El número debe coincidir con la expresión regular (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?. Esto significa que el número puede comenzar con la cadena de tel: (si no se especifica esa cadena, se agregará automáticamente para usted), un signo más (+) y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ext= y el número de extensión.
    
6. En **Servicio de anuncio**, lleve a cabo uno de los siguientes procedimientos: 
    
   - Haga clic en **Anuncio**.
    
   - Haga clic en **Mensajería unificada de Exchange**.
    
7. Si en el paso anterior ha hecho clic en **Anuncio**, proceda de la siguiente manera:
    
    a. En el **FQDN del servidor de destino**, haga clic en **Seleccionar**, haga clic en el identificador de servicio del servicio de aplicación que se ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este rango de números sin asignar y, a continuación, haga clic en **Aceptar**.
    
    b. En **Anuncio**, haga clic en el anuncio que se va a reproducir para este intervalo de números sin asignar.
    
8. Si en el paso anterior hizo clic en **Mensajería unificada de Exchange**, en **Número de teléfono del operador automático**, haga clic en **Seleccionar**, haga clic en el número de teléfono que se va a utilizar para este intervalo de números sin asignar y, a continuación, haga clic en **Aceptar**.
    
9. Haga clic en **Aceptar**.
    
10. En la página **Número sin asignar**, asegúrese de que los intervalos de números sin asignar se disponen según el orden que le interesa. Para cambiar la posición de un intervalo en la tabla, haga clic en uno o más nombres consecutivos en la lista de intervalos y, a continuación, haga clic en la flecha arriba o abajo.
    
    > [!TIP]
    > Skype para Business Server busca en la tabla sin asignar número de arriba a abajo y utiliza el primer rango que coincide con el número sin asignar. Si tiene intervalos superpuestos y un intervalo especifica una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista. 
  
11. Cuando haya ordenado el intervalo de números sin asignar según su conveniencia, haga clic en **Confirmar todo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Usar Skype para negocios de Shell de administración de servidor para configurar números de teléfono sin asignar

1. Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Utilice **CsUnassignedNumber de nuevo** para crear un nuevo rango de números sin asignar. Utilice **Set CsUnassignedNumber** para modificar un rango existente de números sin asignar.
    
    > [!TIP]
    > Si tiene intervalos solapados y desea que se apliquen en un orden específico, incluya el parámetro Prioridad. Se aplicará a la llamada el intervalo con la máxima prioridad. 
  
    En la línea de comandos, realice una de las acciones siguientes:
    
     - Si desea crear un intervalo de números para un servicio de anuncio, ejecute:
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - O, si desea crear un intervalo de números para el Operador automático de mensajería unificada de Exchange, ejecute:
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Por ejemplo:
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     O bien
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

    El siguiente ejemplo muestra cómo modificar los números de un intervalo de números no asignados existente:
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Eliminar un intervalo de números sin asignar

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Usar Skype para Business Server Control Panel para eliminar un intervalo de números sin asignar

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea **Delegar permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.
    
4. En la página **Número sin asignar**, en el campo de búsqueda, escriba la totalidad o parte del nombre del intervalo del número sin asignar que desee eliminar.
    
5. En la lista resultante de intervalos numéricos, haga clic en el nombre, en **Editar** y, a continuación, en **Eliminar**.
    
6. Haga clic en **Confirmar todo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Usar Skype para negocios de Shell de administración de servidor para eliminar un intervalo de números sin asignar

1. Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. En la línea de comandos, escriba lo siguiente:
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Por ejemplo:
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Para obtener más información acerca de las opciones más, consulte [Quitar CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Vea también

#### 

[Nueva CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Conjunto de CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)

