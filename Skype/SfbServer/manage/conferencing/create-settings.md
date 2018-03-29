---
title: Crear opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumen: Aprender a crear valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 2d3bde2c856c85e0795f2e1d43fbb5cf705c7024
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Crear opciones de configuración de reuniones en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear valores de configuración de Skype para Business Server 2015 de reunión.
  
Puede crear valores de configuración de reunión utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor de Business.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Crear valores de configuración de la reunión con Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
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
    
9. Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente. Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB. Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión. Si no se incluye una dirección URL de ayuda personalizada, se mostrará la dirección URL de Ayuda predeterminada de Skype para el negocio en la invitación. 
    
   - Para personalizar el logotipo que aparece en la invitación a la reunión, en **dirección URL del logotipo** introduzca la ubicación del logotipo. El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles. 
    
   - Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, introduzca la ubicación del texto de ayuda.
    
   - Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, introduzca la ubicación del texto legal.
    
   - Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.
    
10. Haga clic en **Confirmar**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Crear valores de configuración de la reunión con Skype para el Shell de administración de servidor empresarial

Para crear opciones de configuración de reunión, use el cmdlet **New-CsMeetingConfiguration**.
  
El siguiente comando crea un conjunto de opciones de configuración de reunión para el sitio de Redmond:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.
  
Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Puede establecer varios valores de propiedad incluyendo varios parámetros. Por ejemplo, el siguiente comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Para obtener más información, incluida una lista completa de los parámetros, consulte [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

