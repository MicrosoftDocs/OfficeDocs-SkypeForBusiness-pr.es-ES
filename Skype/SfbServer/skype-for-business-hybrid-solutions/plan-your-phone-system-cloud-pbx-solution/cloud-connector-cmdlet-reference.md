---
title: Referencia de cmdlets de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: En la siguiente tabla se enumeran los cmdlets de Skype empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359056"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referencia de cmdlets de Cloud Connector
 
> [!Important]
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

En la siguiente tabla se enumeran los cmdlets de Skype empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
  
> [!NOTE]
> Debe ejecutar todos los cmdlets en el equipo host de Cloud Connector, y debe ejecutar la sesión de PowerShell como administrador. 
  
|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versión 1.4.2 y posteriores  <br/> |Realiza una copia de seguridad del servicio de entidad de certificación en un archivo y lo guarda en la carpeta de CA en el directorio compartido del sitio.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Cloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara el servidor host de Cloud Connector para el proceso de actualización colocándolo en modo de mantenimiento. El dispositivo está "drenado"; es decir, todas las llamadas existentes se completarán, pero se rechazarán las llamadas nuevas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Sale del modo de mantenimiento de actualización en el servidor host de Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporta una configuración de Skype empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype empresarial Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta un archivo de configuración de ejemplo (. ini) de Cloud Connector al directorio del dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo para usarlo en su implementación de.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Exporta el certificado de la entidad de certificación raíz a un archivo local en el servidor host de Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera el directorio de trabajo en el servidor host de Cloud Connector. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los registros de un dispositivo de Cloud Connector.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versión 2,1 y posteriores  <br/> |Proporciona información de diagnóstico para el dispositivo de Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Devuelve las credenciales de la implementación actual de Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Devuelve la ruta de acceso del archivo de certificado externo para la implementación de Cloud Connector. El usuario prepara este certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene los archivos de instalación del VHD base y de Cloud Connector. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los registros a nivel de sitio de Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versión 2,0 y posteriores  <br/> |Devuelve la versión de la instancia de Cloud Connector. Get-CCVersion solo se puede usar en la máquina host de Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versión 2,0 y posteriores  <br/> |Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host de Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala el dispositivo de Cloud Connector (incluidas las máquinas virtuales de AD, del almacén de administración central, del servidor de mediación y del servidor perimetral) en el servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Cloud Connector en el servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse antes de que el servicio de administración de Cloud Connector pueda implementarlo y administrarlo. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita el archivo de copia de seguridad del servicio de entidad de certificación " \<SiteRootDirectory\> \CA\SFB CCE root. p12" en la carpeta CA en el directorio compartido del sitio de Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita los certificados de servidor heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo la versión 1.4.2  <br/> |Reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo la versión 1.4.2  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Restablece los servidores de la entidad de certificación para instalar un nuevo certificado de entidad de certificación.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versión 2,1 y posteriores  <br/> |Limpia las credenciales y le solicita que vuelva a escribir todas las credenciales usadas para la implementación actual de Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Busca los registros de llamadas entrantes y salientes en el directorio de registro del equipo de Cloud Connector.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Establece el directorio de trabajo en el servidor host de Cloud Connector. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Establece las credenciales de la implementación actual de Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica la ruta de acceso donde se almacena el certificado del servidor de mediación o el servidor perimetral.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Cloud Connector. La carpeta contendrá los archivos de configuración VHD base y Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Descarga de forma sincrónica el archivo MSI y bits de Cloud Connector.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera el registro de llamadas entrantes y salientes de un dispositivo de Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta el dispositivo en ejecución y cambia a un dispositivo recién implementado o de copia de seguridad.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala el dispositivo de ejecución de Cloud Connector del servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Anula el registro del dispositivo actual de Cloud Connector de un sitio RTC en la configuración de inquilino en línea.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versión 2,0 y posteriores  <br/> |Reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versión 2,0 y posteriores  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
   

