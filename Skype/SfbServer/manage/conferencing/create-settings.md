---
title: Crear una configuración de reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumen: Aprenda a crear valores de configuración de reuniones en Skype empresarial Server.'
ms.openlocfilehash: cd3d207816f352a33fb3fd228e7249d9e5d836b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818611"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Crear una configuración de reunión en Skype empresarial Server
 
**Resumen:** Aprenda a crear parámetros de configuración de reuniones en Skype empresarial Server.
  
Puede crear valores de configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Crear parámetros de configuración de reunión con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:
    
    - Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.
    
    - Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.
    
5. Para redirigir a los participantes que realizaron la llamada desde una red telefónica conmutada (RTC) a través de la sala de espera, desactive la casilla **Los autores de llamadas RTC no pasan por la sala de espera**. Normalmente, los participantes que efectúen la llamada desde la RTC obtendrán acceso directamente a la reunión.
    
6. Para configurar quién puede ser moderador en una reunión, en **Designar como moderador**, lleve a cabo uno de los procedimientos siguientes:
    
   - Para que solo sea moderador el organizador, haga clic en **Ninguno**.
    
   - Para que solo sean moderadores los participantes que pertenezcan a la organización, haga clic en **Compañía**. Esta es la configuración que se aplica normalmente.
    
   - Para que cualquier participante sea moderador, haga clic en **Todos**.
    
7. Para que el moderador pueda seleccionar un tipo de conferencia cuando se programe una reunión, desactive la casilla **Tipo de conferencia asignada de forma predeterminada**. Normalmente, el tipo de conferencia se asigna automáticamente.
    
8. Para evitar que se admitan automáticamente a usuarios anónimos (sin autenticar), desactive la casilla **Admitir usuarios anónimos de forma predeterminada**. Normalmente, los usuarios anónimos se admiten automáticamente en las reuniones.
    
9. Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente. Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB. Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión. Si no incluye una dirección URL de ayuda personalizada, la dirección URL de la ayuda predeterminada para Skype empresarial se mostrará en la invitación. 
    
   - Para personalizar el logotipo que aparece en la invitación a la reunión, en **dirección URL del logotipo** introduzca la ubicación del logotipo. El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles. 
    
   - Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, introduzca la ubicación del texto de ayuda.
    
   - Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, introduzca la ubicación del texto legal.
    
   - Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.
    
10. Haga clic en **Confirmar**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Crear parámetros de configuración de reunión con el shell de administración de Skype empresarial Server

Para crear opciones de configuración de reunión, use el cmdlet **New-CsMeetingConfiguration**.
  
El siguiente comando crea un conjunto de opciones de configuración de reunión para el sitio de Redmond:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.
  
Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Puede establecer varios valores de propiedad incluyendo varios parámetros. Por ejemplo, el siguiente comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Para obtener más información, incluida una lista completa de parámetros, consulte [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

