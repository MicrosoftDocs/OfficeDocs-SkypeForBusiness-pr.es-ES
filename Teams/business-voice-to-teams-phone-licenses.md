---
title: Pasar de Business Voice a licencias de Teams Teléfono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Obtenga información sobre cómo cambiar las licencias de Business Voice a licencias de Teams Teléfono.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9e973d00761e62e62a3c749163f9e6dcaa8a636
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057100"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Pasar de Business Voice a licencias de Teams Teléfono

A finales de junio de 2022, Business Voice se retirará, por lo que [recomendamos a las empresas que cambien a Teléfono Microsoft Teams con plan de llamadas licencias de paquetes](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice agrupa las tres licencias de complementos de Teams siguientes:

- **Teléfono Microsoft Teams** para una Sistema telefónico basada en la nube en Microsoft Teams.
- **Audioconferencia** para conferencias de acceso telefónico local y de salida para reuniones.
- **Planes de llamadas de Microsoft** para llamadas nacionales a conectividad de red telefónica conmutada (RTC).

Los clientes de Business Voice existentes no pasarán automáticamente al nuevo modelo de licencias.

Este artículo es para administradores de TI que necesitan cambiar sus licencias de Business Voice para Teléfono Microsoft Teams y Audioconferencia licencias a la vez que mantienen las mismas capacidades.

> [!WARNING]
> Siga de cerca las instrucciones de este artículo. Si las instrucciones le indican que NO seleccione el botón **Guardar** , no seleccione el botón **Guardar** .
>
> Ahorrar prematuramente puede provocar la pérdida de asignaciones de números de teléfono, planes de marcado, operadores automáticos y colas de llamadas.

## <a name="acquire-new-licenses"></a>Adquirir nuevas licencias

Antes de reemplazar las licencias de Business Voice, primero debe comprar licencias de reemplazo para los usuarios.

Necesitará licencias para proporcionar estas características:

- Audioconferencia
- Sistema telefónico basada en la nube
- Conectividad con RTC

Use la tabla siguiente para determinar qué licencias comprar en función de sus necesidades:

| Plan de licencia antiguo | Plan de licencias recomendado | Descripción |
| ---------------- | ------------------------ | ----------- |
| Business Voice con plan de llamadas | Teams Teléfono con plan de llamadas y Audioconferencia de Microsoft Teams con llamada a EE. UU./CAN | Proporciona capacidades de Sistema telefónico basadas en la nube, un plan de llamadas nacionales con Microsoft como su proveedor de RTC y funcionalidades de acceso telefónico local y de salida para los asistentes a la reunión organizada por un usuario con licencia. |
| Business Voice sin plan de llamadas | Teléfono Teams Estándar y Audioconferencia de Microsoft Teams con acceso telefónico a EE. UU./CAN | Proporciona capacidades de Sistema telefónico basadas en la nube que se pueden combinar con [un plan de llamadas de terceros con un proveedor de RTC mediante Conexión con operador o enrutamiento directo](pstn-connectivity.md) y funcionalidades de acceso telefónico local y de salida a reuniones organizadas por un usuario con licencia. |

## <a name="how-to-update-licenses"></a>Cómo actualizar licencias

Tiene cuatro formas de actualizar sus licencias:

- Actualización de licencia de usuario único a través de Centro de administración de Microsoft 365
- Actualización masiva de licencias de usuario a través de Centro de administración de Microsoft 365
- Actualización masiva de licencias de usuario con un script de PowerShell
- Actualización masiva de licencias de usuario mediante licencias basadas en grupos de Azure

# <a name="option-1-single-user-in-admin-center"></a>[Opción 1: Usuario único en el centro de administración](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Opción 1: Actualización única de licencias de usuario a través de Centro de administración de Microsoft 365

Para actualizar un único usuario, puede usar el Centro de administración de Microsoft 365.

1. Vaya a [admin.microsoft.com](https://admin.microsoft.com/) e inicie sesión con las credenciales de administrador de inquilinos.
1. Vaya a **Usuarios** > **activos y** seleccione el usuario deseado.
1. Seleccione **Administrar licencias de producto** en la barra de herramientas de la lista.
1. En la pantalla **Licencias y aplicaciones** , anule la selección de la licencia de Business Voice.
    > [!IMPORTANT]
    > NO guarde los cambios todavía. Si guarda los cambios sin agregar las nuevas licencias, se quitará el aprovisionamiento de la cuenta de usuario y se quitará la asignación del número de teléfono.
1. Después de anular la selección de Business Voice, compruebe las nuevas licencias de Teams Teléfono y Audioconferencia.
1. Ahora puedes guardar los cambios de forma segura seleccionando **Guardar cambio**.

Las licencias del usuario se actualizarán y no deberían afectar a la disponibilidad del servicio.

# <a name="option-2-bulk-users-in-admin-center"></a>[Opción 2: Usuarios en masa en el centro de administración](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Opción 2: Actualización masiva de licencias de usuario a través de Centro de administración de Microsoft 365

Para actualizar las licencias de varios usuarios en masa, puede usar el Centro de administración de Microsoft 365. Los usuarios seleccionados tendrán la misma asignación de plan de licencia.

1. Vaya a [admin.microsoft.com](https://admin.microsoft.com/) e inicie sesión con las credenciales de administrador de inquilinos.
1. Vaya a **Usuarios** > **activos y** seleccione todos los usuarios deseados.  
1. Seleccione **Administrar licencias de producto** en la barra de herramientas de la lista.
1. En el símbolo del sistema **¿Qué desea hacer con las licencias para estos usuarios?** , seleccione la opción **Reemplazar: Anular la asignación de licencias existentes y asignar licencias nuevas** .
    > [!IMPORTANT]
    > La opción **Reemplazar** quitará todas las licencias existentes de los usuarios seleccionados.  Como resultado, tendrá que seleccionar el estado de licencia deseado para los usuarios, incluidas las demás licencias en uso, como Microsoft 365 Empresa Premium.
    >
    > Además, si los usuarios seleccionados tienen configuraciones de licencia base diferentes, se sobrescribirán con las licencias seleccionadas, lo que puede afectar a otras áreas de Microsoft 365.
    >
    > Para los inquilinos con una configuración de licencia mixta, se recomienda usar la [opción de actualización masiva con un script de PowerShell](#option-3-bulk-user-license-update-using-a-powershell-script).
1. En la pantalla **Licencias y aplicaciones** , anule la selección de la licencia de Business Voice.
    > [!IMPORTANT]
    > NO guarde los cambios todavía. Si guarda los cambios sin agregar las nuevas licencias, se anularán los aprovisionamiento de las cuentas de los usuarios seleccionados y se quitará la asignación del número de teléfono.
1. Después de anular la selección de Business Voice, compruebe las nuevas licencias de Teams Teléfono y Audioconferencia.
1. Ahora puedes guardar los cambios de forma segura seleccionando **Guardar cambio**.
  Las licencias de los usuarios se actualizarán y no deberían afectar a la disponibilidad del servicio.

# <a name="option-3-bulk-users-via-powershell"></a>[Opción 3: Usuarios en masa a través de PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Opción 3: Actualización masiva de licencias de usuario con un script de PowerShell

Reemplazar el plan de licencia de Business Voice con un script de PowerShell es una solución eficaz para la mayoría de los escenarios.  

Para usar este método, siga estos pasos generales:

1. Obtenga los identificadores de plan de licencia específicos del inquilino de sus licencias actuales de Business Voice.
1. Obtenga los identificadores específicos del inquilino de los nuevos planes de licencia de Teams Teléfono y Audioconferencia.
1. Valide si los nuevos planes de licencia tienen los mismos planes de servicio que la licencia de Business Voice actual.
1. Busque usuarios de inquilino con licencia de Business Voice (o modifique el script para incluir un filtro para seleccionar un subconjunto de usuarios, si lo desea).
1. Actualice la configuración de licencia de los usuarios con planes de Teams Teléfono y Audioconferencia.

> [!IMPORTANT]
> El script proporcionado es un ejemplo de código. El script no se debe copiar tal cual y ejecutarse en un espacio empresarial de producción sin probar, validar y personalizar su entorno específico.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Cómo actualizar licencias en masa con PowerShell

1. Instale e importe el módulo de PowerShell de AzureAD.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Conectar a su inquilino de Microsoft 365 y proporcione las credenciales de administrador del inquilino.

    ```powershell
    Connect-AzureAD
    ```

1. Usa el siguiente commandlet para enumerar todos los paquetes de licencias del espacio empresarial.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Use la tabla siguiente para identificar el plan de licencia del complemento Business Voice que se reemplazará.

    | Código SKU | Tipo de licencia |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Business Voice con plan de llamadas - Canadá |
    | BUSINESS_VOICE | Business Voice con plan de llamadas - Reino Unido |
    | BUSINESS_VOICE_MED2_TELCO | Business Voice con plan de llamadas: EE. UU. |
    | BUSINESS_VOICE_DIRECTROUTING | Business Voice sin plan de llamadas |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Business Voice sin plan de llamadas: EE. UU. |

    > [!NOTE]
    > El script proporcionado en este documento asume que tiene un único código SKU para Business Voice en su espacio empresarial.  
    >
    > Si tiene varias SKU de voz empresarial, tendrá que ajustar el script o ejecutarlo varias veces, una vez para cada código SKU.

1. Cree una variable de PowerShell denominada `$skuSourceBV`.
    1. Asegúrese de reemplazar la etiqueta por el `SkuPartNumber` código SKU de Business Voice de su inquilino.
    1. En este ejemplo, usamos el `BUSINESS_VOICE_MED2_TELCO` código SKU.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Use la tabla siguiente para identificar los nuevos códigos SKU de licencia de Teams Teléfono y Audioconferencia.

    | Código SKU | Tipo de licencia |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Teléfono de Teams con plan de llamadas |
    | MCOEV | Teléfono Teams Estándar (sin plan de llamadas) |
    | MCOMEETADV | Audioconferencia |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Audioconferencia de Microsoft Teams seleccionar marcado de salida |

1. Cree variables de PowerShell para almacenar los códigos SKU de Teams Teléfono y Audioconferencia únicos.
    1. Asegúrese de reemplazar la `SkuPartNumber` etiqueta por los códigos SKU que tiene disponibles en su espacio empresarial.
    1. En este ejemplo, usamos los `MCOTEAM_ESSENTIALS` códigos SKU y `MCOMEETADV` .

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Ejecute este script para recopilar los datos del plan de servicio necesarios desde la SKU de origen en objetos únicos.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Antes de proceder, valide si la SKU de origen (Business Voice) y las SKU de destino (Teams Teléfono y Audioconferencia) tienen los mismos planes de servicio incluidos.
    1. Una falta de coincidencia puede desencadenar un cambio de licencia que podría interrumpir los servicios de audioconferencia y voz de los usuarios.
    2. Cree variables para validar si todos los planes de servicio del SKU de origen se reemplazarán por el mismo plan de servicio de destino.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Si la licencia de Business Voice de origen no incluye ningún plan de llamadas, no lo compruebe.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Compruebe si todos los planes de servicio de la SKU de origen tienen un plan de servicio coincidente en la SKU de destino.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. Si falta un plan de servicio en la SKU de destino, podría interrumpir la disponibilidad del servicio para los usuarios y el script debería detener el procesamiento.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Si todo parece correcto, prepare objetos de PowerShell para realizar las operaciones de actualización en objetos de usuario. Use el `AssignedLicenses` objeto para esto.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. A continuación, obtenga la lista de usuarios que tienen asignadas las licencias de Business Voice y guárdala en una lista denominada `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. Ahora, con la nueva lista de usuarios, realice una actividad de actualización para quitar las licencias de Business Voice y agregar las licencias de Teams Teléfono y Audioconferencia con el ``$LicensesToUpdate`` objeto que creó anteriormente.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Si no tiene suficientes licencias de Teams Teléfono y/o Audioconferencia disponibles para reemplazar Business Voice, recibirá el error **Suscripción con guid de SKU no tiene ninguna licencia disponible** durante la asignación de usuarios tan pronto como se agote el grupo de licencias.

### <a name="full-script"></a>Script completo

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Opción 4: Usuarios en masa con licencias basadas en grupos de Azure](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Opción 4: Actualización masiva de licencias de usuario mediante licencias basadas en grupos de Azure

La administración de licencias basada en grupos de Azure le permite asignar suscripciones y planes de servicio a un grupo.

Este método garantiza que:

- Las licencias se asignan a todos los miembros del grupo.
- Si se unen nuevos miembros al grupo se les asignarán las licencias adecuadas.
- Cuando se quitan miembros del grupo, esas licencias también se quitan.

Tendrá que validar [los requisitos de licencia para las licencias basadas en grupos](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

> [!NOTE]
> Para este método, las actualizaciones de licencia deben procesarse en un solo paso.
>
> Se recomienda compilar una lista de grupos existentes que tienen licencias de Business Voice asignadas, seleccionar primero un pequeño grupo de usuarios de prueba y reemplazar la asignación del plan de licencias por los nuevos planes de licencia preferidos.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Cómo actualizar en masa licencias con licencias basadas en grupos

1. Vaya a [portal.azure.com](https://portal.azure.com) e inicie sesión con credenciales de administrador.
1. Vaya a **Azure Active Directory** y, en el menú de la izquierda, seleccione **Licencias**.
1. Para comprobar qué grupos tienen asignadas licencias de Business Voice, elija **Todos los productos** y seleccione el plan de Business Voice.
1. Seleccione **Grupos con licencia** o **Usuarios con licencia**. Encontrará la lista de grupos con licencia en el panel derecho.
1. Seleccione el nombre del grupo para abrir los detalles de la asignación del grupo.
1. Seleccione **Tareas** para modificar las licencias asignadas a este grupo.
1. Active las casillas delante de los planes de licencia que adquirió para reemplazar Business Voice.
1. Desactive la casilla situada delante del plan de licencia de Microsoft 365 Business Voice.
1. Seleccione **Guardar**.
1. Vuelva al grupo seleccionando el nombre del grupo. Verá un banner que indica que **los cambios de licencia están pendientes**.
1. Seleccione **Procesar** de nuevo para forzar la actualización de la asignación de licencias.

---

## <a name="validate-user-license-updates"></a>Validar las actualizaciones de licencias de usuario

Una vez que haya completado el método elegido, valide si las licencias de usuario se han actualizado correctamente.

1. Vaya a la [Centro de administración de Microsoft 365](https://admin.microsoft.com) e inicie sesión con credenciales de administrador.
1. Vaya a **Usuarios** > **activos y** seleccione un usuario de prueba.
1. Seleccione **Administrar licencias de producto** en la barra de herramientas.
1. En la pantalla **Licencias y aplicaciones** , revisa qué licencias les han asignado.

Si todos los usuarios de destino tienen asignadas las licencias correctas, habrá completado la actualización de las licencias de Business Voice para Teams Teléfono y licencias de Audioconferencia.
