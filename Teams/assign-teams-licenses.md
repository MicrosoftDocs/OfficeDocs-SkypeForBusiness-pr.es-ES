---
title: Asignar licencias de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias para características como conferencias de Audio, el sistema de teléfono, y los planes de llamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993632"
---
# <a name="assign-microsoft-teams-licenses"></a>Asignación de licencias de Microsoft Teams

Puede asignar licencias a los usuarios para determinadas características como conferencias de Audio, sistema telefónico y planes de llamada. En este artículo se explica cómo agregar estas licencias de forma masiva y para un usuario individual. 

> [!IMPORTANT]
> Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obtener información acerca de qué planeación las licencias que necesitará comprar y cómo comprar, dependiendo de su Office 365, por lo que los usuarios obtener conferencias de Audio, los números gratuitos y la posibilidad de llamar a números de teléfono fuera de su negocio.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias

Aquí es lo que necesita saber antes de asignar licencias de conferencias de Audio, sistema telefónico y planeación de la llamada.

- **¿Está usando conectividad RTC local para los usuarios híbridos?** Si es así, sólo necesita asignar una licencia de sistema telefónico. NO debe asignar un Plan de llamada.

- **Latencia después de la asignación de licencias**: debido a la latencia entre Office 365 y Microsoft Teams, puede demorar hasta 24 horas para un usuario que se asignará a una llamada a Plan después de asignar una licencia. Si después de 24 horas el usuario no está asignado a una llamada a Plan, por favor, [póngase en contacto con soporte técnico para productos de negocio: Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto. Si necesita comprar más licencias de planeación de la llamada, elija **comprar más**.

- **Pasos siguientes**: después de asignar licencias de planeación de la llamada a los usuarios, necesitará obtener sus números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización. Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Asigna una licencia de sistema telefónico y planeación de la llamada a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Asignación de licencias de sistema telefónico y llamar a planear de forma masiva

1. Instale el Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW). ¿No tiene instalado el módulo? Vea [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.

2. Instale el Módulo Microsoft Azure Active Directory. ¿No tiene instalado el módulo? Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [administrar Windows Azure con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Sistema telefónico y otra de Plan de llamadas nacionales.

El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en cursiva (vea [sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para secuencias de comandos](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), después en el ejemplo).

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para scripting

| Nombre del producto | Nombre de la parte SKU |
|--------------|---------------|
| Enterprise E5 (con Sistema telefónico) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Sistema telefónico | MCOEV |
| Plan de llamadas internacionales nacionales & | MCOPSTN2 |
| Nacionales llamar a planear (3000 minutos por usuario y mes para Estados Unidos/PR/CA, 1200 minutos por usuario y mes para países de la UE) | MCOPSTN1 |
| Nacionales llamar a planear (120 minutos por usuario y mes para cada país) </br>*Nota: este plan no está disponible en Estados Unidos*. | MCOPSTN5 |
| Nacionales llamar a planear (240 minutos por usuario y mes para cada país) </br>*Nota: este plan no está disponible en Estados Unidos*. | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Conferencias de audio: sugerencias y secuencias de comandos para la asignación de licencias

Aquí es lo que necesita saber antes de la asignación de licencias de conferencias de Audio.

- **Proveedor de conferencia de audio de terceros**: si ya alguien está configurado para usar un proveedor de conferencia de audio de terceros, cuando se asigna una licencia de conferencias de Audio, se cambiarán para usar Microsoft como el proveedor de conferencia de audio. Puede volver a cambiar al usuario al proveedor de terceros.

- **Pasos siguientes**: después de asignar licencias de conferencias de Audio, es necesario asignarle un proveedor de conferencias de audio. Vea [Asignar Microsoft como proveedor de conferencias de audio](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Asignar una licencia de conferencias de Audio a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Asignar licencias de conferencias de Audio de forma masiva

1. Descargue e instale [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Descargue e instale el Módulo Microsoft Azure Active Directory. Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [administrar Windows Azure con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en cursiva. Vea [los nombres de producto de conferencias de Audio o SKU usadas para secuencias de comandos](#audio-conferencing-product-names-or-skus-used-for-scripting) para todos los nombres de producto.

En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de conferencias de Audio.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de productos de conferencia de audio o SKU usadas para scripting

| Nombre del producto | Nombre de la parte SKU |
|--------------|---------------|
| Conferencias de audio (suscripción) | MCOMEETADV | 
| Audio conferencia de pago por minuto (retenidos)</br>*Nota: requiere comunicaciones créditos necesario configurar y habilitar*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (sin Audioconferencia) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| E5 Enterprise (con las conferencias de Audio) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Créditos de comunicaciones

Aquí es lo que necesita saber antes de la asignación de licencias de créditos de comunicaciones.

- **Los clientes de empresa E5**: incluso si los usuarios se asignan las licencias de empresa E5, aún se recomienda asígneles licencias de créditos de comunicaciones.

- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Asigna una licencia de créditos de comunicaciones para un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Asignar licencias de créditos de comunicaciones de forma masiva

Eche un vistazo en el script de ejemplo para la asignación de licencias de conferencias de Audio. Para actualizarlo con la información de asignación de licencias de créditos de comunicaciones.

## <a name="related-topics"></a>Temas relacionados

[Configurar planes de llamadas](set-up-calling-plans.md)
</br>
[Agregar fondos y administrar los créditos de comunicaciones](add-funds-and-manage-communications-credits.md)
