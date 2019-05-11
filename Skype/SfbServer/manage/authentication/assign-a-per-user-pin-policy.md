---
title: Asignar una directiva de PIN por usuario en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Resumen: Fase AV OAuth certificados y de Skype para Business Server.'
ms.openlocfilehash: 777944be2a2db32e4662b8afecac0023bdd2ab91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902670"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Asignar una directiva de PIN por usuario en Skype para Business Server

**Resumen:** Fase AV y OAuth certificados para Skype para Business Server.
  
La directiva de conferencia de acceso telefónico identificación personal (PIN) de número es uno de los parámetros individuales de una cuenta de usuario que se pueden configurar en el Skype para el Panel de Control de servidor empresarial.
  
La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.
  
Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Para asignar una directiva de PIN por usuario

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Use uno de los métodos siguientes para encontrar a un usuario:
    
   - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
   - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
6. Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    
    > [!TIP]
    > Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en **Acciones** y, después, en **Asignar directivas**. 
  
7. En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:
    
    > [!NOTE]
    > Debido a que hay varias directivas que se pueden configurar mediante el cuadro de diálogo **Asignar directivas** , ** \<mantener tal como está\> ** está seleccionada de manera predeterminada para todas las directivas en el cuadro de diálogo. Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.
  
   - Permitir Skype para Business Server elija automáticamente la directiva de nivel global o, si está definida, la directiva de nivel de sitio.
    
   - Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.
    
     > [!TIP]
     > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en **Ver** para ver los derechos y permisos de usuario definidos en la directiva.
  
8. Cuando haya terminado, haga clic en **Aceptar**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de PIN por usuario mediante Cmdlets de Windows PowerShell

Puede asignar directivas de PIN por usuario mediante el uso de Windows PowerShell y el cmdlet **Grant-CsPinPolicy** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Asignar una directiva de PIN por usuario a un único usuario

- El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Asignar una directiva de PIN por usuario a varios usuarios

- El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener información detallada sobre el parámetro LdapFilter que se usa en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Quitar la asignación de una directiva de PIN por usuario

- El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Para obtener información detallada, vea [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Vea también

[Crear una nueva directiva PIN en Skype para Business Server](create-a-new-pin-policy.md)
