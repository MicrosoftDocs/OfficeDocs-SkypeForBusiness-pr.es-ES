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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: En la tabla siguiente se enumeran los cmdlets de Skype for Business Edición de conector de nube con una breve descripción y vínculos a más información.
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676172"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referencia de cmdlets de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización se haya actualizado a Teams, aprenda a conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).

En la tabla siguiente se enumeran los cmdlets de Skype for Business Edición de conector de nube con una breve descripción y vínculos a más información.
  
> [!NOTE]
> Debe ejecutar todos los cmdlets en la máquina host de Cloud Connector y debe ejecutar la sesión de PowerShell como administrador. 
  
|Nombre del cmdlet**|Descripción|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Versión 1.4.2 y posteriores|Realiza una copia de seguridad del servicio de entidad de certificación en un archivo y lo guarda en la carpeta ca del directorio del recurso compartido de sitio.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación deCloud Connector.|
|[Enter-CcUpdate](enter-ccupdate.md)|Prepara el servidor host de Cloud Connector para el proceso de actualización colocándolo en modo de mantenimiento. El dispositivo está "purgado"; es decir, se completarán todas las llamadas existentes, pero se rechazarán las llamadas nuevas.|
|[Exit-CcUpdate](exit-ccupdate.md)|Sale del modo de mantenimiento de actualización en el servidor host de Cloud Connector.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Exporta una configuración de Skype for Business Edición de conector de nube a un archivo local en el servidor host de Skype for Business Edición de conector de nube.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Exporta un archivo de configuración de ejemplo de Cloud Connector (.ini) al directorio del dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se va a usar para la implementación.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Versión 1.4.2 y posteriores|Exporta el certificado de ca raíz a un archivo local en el servidor host de Cloud Connector.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Recupera el directorio de trabajo en el servidor host de Cloud Connector. Todos los archivos de implementación se almacenan en este directorio.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Muestra el directorio actual donde se almacenan los registros de un dispositivo de Cloud Connector.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Versión 2.1 y posteriores|Proporciona información de diagnóstico para el dispositivo de Cloud Connector.|
|[Get-CcCredential](get-cccredential.md)|Devuelve la credencial de la implementación actual de Cloud Connector.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Devuelve la ruta de acceso del archivo de certificado externo para la implementación de Cloud Connector. El usuario prepara este certificado.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene los archivos de instalación base vhd y Cloud Connector. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Muestra el directorio actual donde se almacenan los registros de nivel de sitio para Cloud Connector.|
|[Get-CcVersion](get-ccversion.md) <p> Versión 2.0 y posteriores|Devuelve la versión en la instancia de Cloud Connector. Get-CCVersion solo se puede usar en la máquina host de Cloud Connector.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Versión 2.0 y posteriores|Importa la configuración de Skype for Business Edición de conector de nube de un archivo local al servidor host de Cloud Connector.|
|[Install-CcAppliance](install-ccappliance.md)|Instala el dispositivo Cloud Connector( incluidas las máquinas virtuales AD, Central Management Store, Mediation Server y Edge Server) en el servidor host.|
|[Publish-CcAppliance](publish-ccappliance.md)|Obtiene información de alta disponibilidad de la configuración del inquilino en línea y la publica en el dispositivo Cloud Connector en el servidor host.|
|[Register-CcAppliance](register-ccappliance.md)|Registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse antes de que pueda implementarse y administrarse mediante el servicio de administración de Cloud Connector.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Versión 1.4.2 y posteriores|Quita el archivo de copia de seguridad del servicio de entidad de certificación "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" en la carpeta CA del directorio del recurso compartido de sitio para Cloud Connector.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Versión 1.4.2 y posteriores|Quita los certificados de servidor heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew CcServerCertificate.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Solo versión 1.4.2|Vuelve a instalar el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Solo versión 1.4.2|Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Versión 1.4.2 y posteriores|Restablece los servidores de entidad de certificación para instalar un nuevo certificado de entidad de certificación.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Versión 2.1 y posteriores|Limpia las credenciales y le pide que vuelva a escribir todas las credenciales usadas para la implementación actual de Cloud Connector.|
|[Search-CcLog](search-cclog.md)|Busca los registros de llamadas entrantes y salientes en el directorio de registro del dispositivo de Cloud Connector.|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Establece el directorio de trabajo en el servidor host de Cloud Connector. Todos los archivos de implementación se almacenan en este directorio.|
|[Set-CcCredential](set-cccredential.md)|Establece la credencial de la implementación actual de Cloud Connector.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Especifica la ruta de acceso donde se almacena el certificado para el servidor de mediación o el servidor perimetral.|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para Cloud Connector. La carpeta contendrá los archivos de configuración base VHD y Cloud Connector.|
|[Start-CcDownload](start-ccdownload.md)|Descarga los bits de Cloud Connector y el archivo msi de forma sincrónica.|
|[Start-CcLogging](start-cclogging.md)|Genera el registro de llamadas entrante y saliente para un dispositivo de Cloud Connector.|
|[Stop-CcLogging](stop-cclogging.md)|Deja de generar el registro de llamadas entrantes y salientes para un dispositivo de Cloud Connector.|
|[Switch-CcVersion](switch-ccversion.md)|Desconecta el dispositivo en ejecución y cambia a un dispositivo de copia de seguridad o recién implementado.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Desinstala el dispositivo de Cloud Connector en ejecución del servidor host.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Anula el registro del dispositivo de Cloud Connector actual de un sitio RTC en la configuración del inquilino en línea.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Versión 2.0 y posteriores|Vuelve a instalar el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Versión 2.0 y posteriores|Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.|
