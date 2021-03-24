---
title: Asignar una directiva de PIN por usuario en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Summary: Stage AV and OAuth certificates for Skype for Business Server.'
ms.openlocfilehash: a5cd533dccffb878fad7d7562ded3da301fc0ce3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096836"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Asignar una directiva de PIN por usuario en Skype Empresarial Server

**Resumen:** Certificados de FASE AV y OAuth para Skype Empresarial Server.
  
La directiva de número de identificación personal (PIN) de conferencia de acceso telefónico local es una de las configuraciones individuales de una cuenta de usuario que se pueden configurar en el Panel de control de Skype Empresarial Server.
  
La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.
  
Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Para asignar una directiva de PIN por usuario

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Utilice uno de los métodos siguientes para encontrar a un usuario:
    
   - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
   - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
6. Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    
    > [!TIP]
    > Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en **Acciones** y después en **Asignar directivas**. 
  
7. En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:
    
    > [!NOTE]
    > Dado que hay varias directivas que  puede configurar mediante el cuadro de diálogo Asignar directivas, está seleccionada de forma predeterminada para todas las **\<Keep as is\>** directivas del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.
  
   - Permitir que Skype Empresarial Server elija automáticamente la directiva de nivel global o, si se define, la directiva de nivel de sitio.
    
   - Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.
    
     > [!TIP]
     > Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en **Ver** para ver los derechos y permisos de usuario definidos en la directiva.
  
8. Cuando haya terminado, haga clic en **Aceptar**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva Per-User PIN mediante cmdlets de Windows PowerShell datos

Puede asignar directivas de PIN por usuario mediante Windows PowerShell y el cmdlet **Grant-CsPinPolicy.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Asignar una directiva de PIN por usuario a un único usuario

- El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Asignar una directiva de PIN por usuario a varios usuarios

- El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, vea [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Quitar la asignación de una directiva de PIN por usuario

- El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Para obtener más información, [vea Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Ver también

[Crear una nueva directiva de PIN en Skype Empresarial Server](create-a-new-pin-policy.md)