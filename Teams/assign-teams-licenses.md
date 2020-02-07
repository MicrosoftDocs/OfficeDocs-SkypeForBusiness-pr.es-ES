---
title: Asignar licencias de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias de características como audioconferencia, sistema telefónico y planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 967b67c1d8bc92009e1319260373c9b8abc52b99
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826318"
---
# <a name="assign-microsoft-teams-licenses"></a>Asignar licencias de Microsoft Teams

Puede asignar licencias a los usuarios para características como audioconferencia, sistema telefónico y planes de llamadas. En este artículo se explica cómo agregar estas licencias a granel y para un usuario individual. 

> [!IMPORTANT]
> Consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obtener información sobre las licencias que necesita comprar y sobre cómo obtenerlas, en función de su plan 365 de Office, para que los usuarios reciban conferencias de audio, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su empresa.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias

Esto es lo que debe saber antes de asignar las conferencias de audio, el sistema telefónico y las licencias del plan de llamadas.

- **¿Está usando conectividad RTC local para los usuarios híbridos?** Si es así, solo tiene que asignar una licencia de sistema telefónico. NO debe asignar un plan de llamadas.

- **Latencia después**de asignar licencias: debido a la latencia entre Office 365 y Microsoft Teams, un usuario puede tardar hasta 24 horas en asignarse a un plan de llamadas después de asignar una licencia. Si, después de 24 horas, el usuario no tiene asignado un plan de llamadas, [póngase en contacto con el soporte técnico para productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto. Si necesita comprar más licencias del plan de llamadas, elija **comprar más**.

- **Pasos siguientes**: después de asignar las licencias del plan de llamadas a los usuarios, tendrá que obtener los números de teléfono de la organización y, a continuación, asignar esos números a las personas de su organización. Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Asignar un sistema telefónico y una licencia de plan de llamadas a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Asignar licencias de plan y sistema telefónico a granel

1. Instale el Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW). ¿No tiene instalado el módulo? Consulte [ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.

2. Instale el Módulo Microsoft Azure Active Directory. ¿No tiene instalado el módulo? Consulte [administrar Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y la sintaxis del cmdlet.

3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Sistema telefónico y otra de Plan de llamadas nacionales.

El nombre de las licencias o nombres de los productos en la secuencia de comandos se muestra en cursiva (consulte el [sistema telefónico y los nombres de los productos o SKU usados para scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), después del ejemplo).

```
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Sistema telefónico y planes de llamadas nombres de producto o SKU usados para scripting

| Nombre del producto | Nombre de la parte SKU |
|--------------|---------------|
| Enterprise E5 (con Sistema telefónico) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Sistema telefónico | MCOEV |
| Plan de llamadas nacionales & internacionales | MCOPSTN2 |
| Plan de llamadas nacionales (3000 minutos por usuario y mes para Estados Unidos/PR/CA, 1200 minutos por usuario y mes para países de la UE) | MCOPSTN1 |
| Plan de llamadas nacionales (120 minutos por usuario/mes por país) </br>*Nota: este plan no está disponible en nosotros*. | MCOPSTN5 |
| Plan de llamadas nacionales (240 minutos por usuario/mes por país) </br>*Nota: este plan no está disponible en nosotros*. | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferencias: sugerencias y scripts para asignar licencias

Esto es lo que debe saber antes de asignar licencias de audioconferencia.

- **Proveedor de servicios de audioconferencia de terceros**: si alguien ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de audioconferencia, se cambiará para usar Microsoft como el proveedor de servicios de audioconferencia. Puede volver a cambiar al usuario al proveedor de terceros.

- **Pasos siguientes**: después de asignar las licencias de audioconferencia, debe asignar un proveedor de servicios de audioconferencia. Consulte [asignar Microsoft como el proveedor de servicios de audioconferencia](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Asignar una licencia de audioconferencia a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Asignar licencias de audioconferencia en masa

1. Descargue e instale [el ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Descargue e instale el Módulo Microsoft Azure Active Directory. Consulte [administrar Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y la sintaxis del cmdlet.

Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

El nombre de las licencias o nombres de los productos en la secuencia de comandos se muestra en cursiva. Ver los nombres de los [productos de audioconferencia o las SKU usadas para los scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) de todos los nombres de productos.

Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de audioconferencia.

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de los productos de audioconferencias o SKU usados para scripting

| Nombre del producto | Nombre de la parte SKU |
|--------------|---------------|
| Audioconferencia (suscripción) | MCOMEETADV | 
| Pago de audioconferencias por minuto (pagar a medida que hablas)</br>*Nota: es necesario configurar y habilitar el crédito*de las comunicaciones. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (sin Audioconferencia) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (con audioconferencias) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Créditos de comunicaciones

Esto es lo que debe saber antes de asignar licencias de créditos de comunicaciones.

- **Clientes de Enterprise E5**: incluso si los usuarios tienen asignadas licencias Enterprise E5, le recomendamos que les asigne licencias de créditos para comunicaciones.

- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Asignar una licencia de créditos de comunicaciones a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Asignar créditos de comunicaciones licencias a granel

Eche un vistazo a la secuencia de comandos de ejemplo para asignar licencias de audioconferencia. Actualícelo con la información para asignar licencias de créditos de comunicaciones.

## <a name="related-topics"></a>Temas relacionados

[Configurar planes de llamadas](set-up-calling-plans.md)
</br>
[Agregar fondos y administrar los créditos de comunicaciones](add-funds-and-manage-communications-credits.md)
