---
title: Crear o modificar un intervalo de números sin signo en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Crear, modificar o eliminar intervalos de números sin signo para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial. Esto afecta a la forma en que se controlan las llamadas a números sin signo.
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837090"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Crear o modificar un intervalo de números sin signo en Skype Empresarial Server
 
Crear, modificar o eliminar intervalos de números sin signo para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial. Esto afecta a la forma en que se controlan las llamadas a números sin signo.
  
Skype Empresarial Server le permite decir qué sucede con las llamadas entrantes a números de teléfono válidos para su organización, pero que no están asignados a un usuario o a un teléfono. Para controlar este tipo de llamadas, configure una tabla de números sin signo. Puede usar la tabla para enrutar las llamadas a una aplicación de anuncio o a un servidor de mensajería unificada de Exchange.
  
La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurar números de teléfono sin signo

Use uno de los siguientes procedimientos para configurar intervalos de números sin signo para la aplicación Anuncio.
  
> [!IMPORTANT]
> Antes de configurar la tabla de números sin signo, el sistema ya debe tener anuncios definidos o una configuración de mensajería unificada de Exchange Operador automático configuración. 
  
> [!TIP]
> Cuando alguien llama a un número sin signo, Skype Empresarial Server busca en la tabla de números sin signo de arriba abajo y usa el primer intervalo correspondiente. Por tanto, si quiere que una determinada acción se realice como último recurso, deberá especificarla para el último intervalo en la tabla. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar el Panel de control de Skype Empresarial Server para configurar números de teléfono sin signo

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.
    
4. En la página **Número sin asignar**, siga uno de estos procedimientos:
    
   - Para crear un nuevo intervalo de números, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.
    
     > [!NOTE]
     > Una vez haya confirmado el nuevo intervalo de números sin asignar para la base de datos, no podrá cambiar este nombre. 
  
   - Para modificar un intervalo de números existentes, escriba en el campo de búsqueda todo el intervalo de números o parte de él. En la lista de intervalos numéricos resultante, haga clic en el nombre que desee, en **Editar** y en **Mostrar detalles**.
    
5. En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo, y en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.
    
   - El número inicial del intervalo debe ser menor o igual al número final del intervalo.
    
   - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.
    
   - ¿El número debe coincidir con la expresión regular (tel:)?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. Esto significa que el número puede comenzar con la cadena tel: (si no especifica esa cadena, se agregará automáticamente), un signo más (+) y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".
    
6. En **Servicio de anuncio**, lleve a cabo uno de los siguientes procedimientos: 
    
   - Haga clic en **Anuncio**.
    
   - Haga clic en **Mensajería unificada de Exchange**.
    
7. Si, en el paso anterior, ha hecho clic en **Anuncio**, proceda de la siguiente manera:
    
    a. En **FQDN del servidor de destino**, haga clic en **Seleccionar**, haga clic en el Id. de servicio del servicio de aplicaciones que ejecute la aplicación Anuncio que se va a encargar de las llamadas entrantes correspondientes a este intervalo de números sin asignar y, a continuación, haga clic en **Aceptar**.
    
    b. En **Anuncio**, haga clic en el anuncio que se va a reproducir para este intervalo de números sin asignar.
    
8. Si, en el paso anterior, hizo clic en **Mensajería unificada de Exchange**, en **Número de teléfono del operador automático**, haga clic en **Seleccionar**, haga clic en el número de teléfono que se va a utilizar para este intervalo de números sin asignar y, a continuación, en **Aceptar**.
    
9. Haga clic en **Aceptar**.
    
10. En la página **Número sin asignar**, asegúrese de que los intervalos de números sin asignar se disponen según el orden que desee. Para cambiar la posición de un intervalo en la tabla, haga clic en uno o más nombres consecutivos en la lista de intervalos y, a continuación, haga clic en la flecha arriba o abajo.
    
    > [!TIP]
    > Skype Empresarial Server busca en la tabla de números sin signo de arriba abajo y usa el primer intervalo que coincide con el número sin signo. Si tiene intervalos superpuestos y un intervalo especifica una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista. 
  
11. Cuando haya ordenado el intervalo de números sin asignar según su conveniencia, haga clic en **Confirmar todo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Para usar el Shell de administración de Skype Empresarial Server para configurar números de teléfono sin signo

1. Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados.**
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Use **New-CsUnassignedNumber** para crear un nuevo intervalo de números no asignados. Use **Set-CsUnassignedNumber** para modificar un intervalo de números no asignados existente.
    
    > [!TIP]
    > Si tiene intervalos solapados y desea que se apliquen en un orden específico, incluya el parámetro Prioridad. Se aplicará a la llamada el intervalo con la máxima prioridad. El valor 0 representa la prioridad más alta.
  
    En la línea de comandos, realice una de las acciones siguientes:
    
   - Si desea crear un intervalo de números para un servicio de anuncio, ejecute:
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - O, si desea crear un intervalo de números para el Operador automático de mensajería unificada de Exchange, ejecute:
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Por ejemplo:
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     O bien
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     El siguiente ejemplo muestra cómo modificar los números de un intervalo de números no asignados existente:
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Eliminar un intervalo de números sin signo

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Para usar el Panel de control de Skype Empresarial Server para eliminar un intervalo de números sin signo

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.
    
4. En la página **Número sin asignar**, en el campo de búsqueda, escriba la totalidad o parte del nombre del intervalo del número sin asignar que desee eliminar.
    
5. En la lista resultante de rangos de números, haga clic en el nombre, en **Editar** y, a continuación, en **Eliminar**.
    
6. Haga clic en **Confirmar todo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Para usar el Shell de administración de Skype Empresarial Server para eliminar un intervalo de números sin signo

1. Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados.**
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. En la línea de comandos, escriba lo siguiente:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Por ejemplo:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Para obtener más información sobre las opciones, [vea Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Ver también

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
