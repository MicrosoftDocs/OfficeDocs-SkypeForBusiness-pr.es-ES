---
title: Crear directivas de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumen: Aprenda a crear directivas de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 323a50ab779e772ca6149dc4c151f9d42d55df66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304015"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Crear directivas de conferencia en Skype empresarial Server
 
**Resumen:** Aprenda a crear directivas de conferencia en Skype empresarial Server.
  
Puede crear directivas de conferencia con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Crear directivas de conferencia con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. Haga clic en **Nuevo** y, luego, siga uno de estos procedimientos:
    
   - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Directiva de conferencia nueva**, en **Nombre**, escriba un nombre descriptivo para la directiva.
    
   - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.
    
     > [!NOTE]
     > El nombre del sitio pasa a ser el nombre de la directiva de conferencia y no se puede cambiar. 
  
5. En **Descripción**, escriba una descripción para la directiva.
    
6. En **Directiva de organizadores**, en **Tamaño máximo de la reunión**, escriba el número máximo de usuarios que desea que participen en una reunión. De manera predeterminada, el tamaño máximo de la reunión se establece en 250.
    
7. Para impedir que los usuarios inviten a usuarios anónimos a las reuniones, desactive la casilla **Permitir a los participantes invitar a usuarios anónimos**. Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de su organización y que, por consiguiente, no se autentican. De manera predeterminada, los participantes pueden invitar a usuarios anónimos a las reuniones.
    
8. En **Grabación**, lleve a cabo uno de los siguientes procedimientos:
    
   - Para impedir que los participantes graben reuniones, haga clic en **Ninguna**. Esta es la configuración predeterminada.
    
   - Para permitir que los participantes graben reuniones, haga clic en **Habilitar grabación**.
    
9. Para permitir que los participantes externos graben reuniones, active la casilla **Permitir a los participantes federados y anónimos grabar**. Generalmente, los participantes externos no pueden grabar las reuniones.
    
10. En **Audio/vídeo**, lleve a cabo uno de los siguientes procedimientos:
    
    - Para impedir el uso de audio y vídeo, haga clic en **Ninguno**.
    
    - Para permitir el uso de audio pero no de vídeo, haga clic en **Habilitar audio IP**.
    
    - Para permitir el uso de audio y de vídeo, haga clic en **Habilitar audio y vídeo IP**. Esta es la configuración predeterminada.
    
11. Si opta por permitir el uso de audio en **Audio/vídeo**, realice uno de los procedimientos siguientes:
    
    - Para impedir que los usuarios participen en la reunión mediante acceso telefónico, desactive la casilla **Habilitar conferencia de acceso telefónico local RTC**. De manera predeterminada, los usuarios pueden acceder telefónicamente a las reuniones a través de la red telefónica conmutada (RTC).
    
    - Si permite que los usuarios accedan telefónicamente a las reuniones y desea permitir que usuarios no autenticados (anónimos) se unan a una reunión por aceptación de llamada, active la casilla **Permitir acceso telefónico a los participantes anónimos**. Con la aceptación de llamadas, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión. De manera predeterminada, los usuarios anónimos no pueden participar en una reunión por aceptación de llamada.
    
12. Si opta por permitir el uso de vídeo en **Audio/vídeo**, active **Permitir varias secuencias de vídeo**.
    
13. En **Colaboración de datos**, lleve a cabo uno de los siguientes procedimientos:
    
    - Para impedir la colaboración de datos, haga clic en **Ninguna**.
    
    - Para permitir la colaboración de datos, haga clic en **Habilitar colaboración de datos**. Esta es la configuración predeterminada.
    
14. Si opta por permitir la colaboración de datos en **Colaboración de datos**, realice uno de los procedimientos siguientes:
    
    - Para impedir descargas externas, desactive la casilla **Permitir a los participantes federados y anónimos descargar contenido**. De manera predeterminada, los usuarios externos pueden descargar contenido.
    
    - Para impedir la transferencia de archivos, desactive la casilla **Permitir a los participantes transferir archivos**. De manera predeterminada, los usuarios pueden transferir archivos.
    
    - Para impedir el uso de anotaciones, desactive la casilla **Habilitar anotaciones**. Para usar anotaciones en las presentaciones de PowerPoint compartidas, desactive la casilla **Habilitar anotaciones de PowerPoint**. Normalmente, las anotaciones se permiten.
    
    - Para impedir el uso de sondeos, desactive la casilla **Habilitar sondeos**. De manera predeterminada, se permiten los sondeos.
    
15. En **Uso compartido de aplicaciones**, lleve a cabo uno de los siguientes procedimientos:
    
    - Para impedir el uso compartido de aplicaciones, haga clic en **Deshabilitar el uso compartido de aplicaciones**.
    
    - Para permitir el uso compartido de aplicaciones, haga clic en **Habilitar el uso compartido de aplicaciones**. Esta es la configuración predeterminada.
    
16. Si opta por permitir el uso compartido de aplicaciones en **Uso compartido de aplicaciones**, realice uno de los procedimientos siguientes:
    
    - Para impedir que los participantes en una reunión controlen el uso compartido de aplicaciones, desactive la casilla **Permitir a los participantes asumir el control**. De manera predeterminada, los participantes pueden controlar el uso compartido de las aplicaciones.
    
    - Si opta por permitir que los participantes de las reuniones controlen el uso compartido de aplicaciones, seleccione la casilla **Permitir a los participantes federados y anónimos asumir el control** para permitir que los usuarios externos controlen el uso compartido de aplicaciones. De manera predeterminada, los usuarios externos no pueden controlar el uso compartido de las aplicaciones.
    
17. En **Directiva de participantes**, siga uno de estos procedimientos:
    
    - Para impedir el uso compartido de las aplicaciones y del escritorio, haga clic en **Deshabilitar el uso compartido de aplicaciones y escritorio**.
    
    - Para permitir el uso compartido de las aplicaciones pero no el uso compartido del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones**.
    
    - Para permitir el uso compartido de las aplicaciones y del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones y escritorio**. Esta es la configuración predeterminada.
    
18. Para impedir la transferencia de archivos punto a punto, desactive la casilla **Habilitar la transferencia de archivos punto a punto**. De manera predeterminada, se permite la transferencia de archivos punto a punto.
    
19. Para permitir la grabación punto a punto, active la casilla **Habilitar grabación punto a punto**. De manera predeterminada, no se permite la grabación punto a punto.
    
20. Para permitir que los participantes se unan con varias secuencias de vídeo, active la casilla **Permitir que los participantes se unan con varias secuencias de vídeo**. De manera predeterminada, se permiten varias secuencias de vídeo.
    
21. Haga clic en **Confirmar**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Crear directivas de conferencia con el shell de administración de Skype empresarial Server

Para crear directivas de conferencia, use el cmdlet **New-CsConferencingPolicy**.
  
En el ejemplo siguiente se crea una nueva Directiva de conferencia con la identidad SalesConferencingPolicy. Esta directiva usará todos los valores predeterminados de una directiva de conferencia, excepto uno: MaxMeetingSize. En este ejemplo, el tamaño máximo para una reunión se establecerá en 50, en lugar del valor predeterminado 250:
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
  

