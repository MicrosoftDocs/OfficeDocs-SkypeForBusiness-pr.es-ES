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
description: En la siguiente tabla se muestran los cmdlets de Skype Empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
ms.openlocfilehash: c82d81fe19af7c0f305ce18e0bbce83f944b5d73
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803720"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
En la siguiente tabla se muestran los cmdlets de Skype Empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
  
> [!NOTE]
> Debe ejecutar todos los cmdlets en el equipo host del conector de nube y debe ejecutar la sesión de PowerShell como administrador. 
  
|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versión 1.4.2 y posteriores  <br/> |Crea una copia de seguridad del servicio de la entidad de certificación en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Cloud Connector.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara el servidor host del conector de nube para el proceso de actualización al ponerlo en modo de mantenimiento. El dispositivo está "drenado"; es decir, todas las llamadas existentes se completarán, pero se rechazarán las llamadas nuevas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Sale del modo de mantenimiento de la actualización en el servidor host del conector de nube.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exporta una configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta un archivo de configuración de ejemplo del conector de nube (. ini) al directorio del equipo de un dispositivo del conector de nube. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versión 1.4.2 y posteriores   <br/> |Exporta el certificado de la entidad emisora raíz a un archivo local en el servidor host del conector de nube.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera el directorio de trabajo en el servidor host del conector de nube. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los registros para un dispositivo de conector de nube.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versión 2,1 y posteriores  <br/> |Proporciona información de diagnóstico para el dispositivo de conector de nube.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Devuelve la credencial de la implementación del conector de nube actual.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Devuelve la ruta de acceso del archivo del certificado externo para la implementación del conector en la nube. El usuario debe preparar este certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene los archivos de instalación VHD básicos y Cloud Connector. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de conector de nube.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los registros de nivel de sitio para Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versión 2.0 y posteriores  <br/> |Devuelve la versión en la instancia de Cloud Connector. Get-CCVersion solo se puede usar en la máquina host de Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versión 2.0 y posteriores  <br/> |Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host del conector de nube.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala el dispositivo de conector de nube, que incluye las máquinas virtuales de AD, el almacén central de administración, el servidor de mediación y el servidor perimetral, en el servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtiene información de alta disponibilidad de la configuración del inquilino en línea y la publica en el dispositivo de conector de nube en el servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Un dispositivo debe registrarse antes de que el servicio de administración de conector de nube pueda implementarlo y administrarlo. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita el archivo de copia de seguridad servicio\<de\>la entidad emisora de certificados "SiteRootDirectory \CA\SfB CCE root. p12" en la carpeta de CA del directorio compartido del sitio para el conector de nube.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita los certificados de servidores heredados del Almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo la versión 1.4.2  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo la versión 1.4.2  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Restablece los servidores de la entidad de certificación para instalar un nuevo certificado de entidad de certificación.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versión 2,1 y posteriores  <br/> |Limpia las credenciales y le pide que vuelva a escribir todas las credenciales usadas para la implementación del conector de nube actual.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Busca los registros de llamadas entrantes y salientes en el directorio de registro del equipo del conector de nube  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Establece el directorio de trabajo en el servidor host del conector de nube. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Establece la credencial de la implementación del conector de nube actual.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Cloud Connector. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Descarga los bits de conector de la nube y el archivo MSI de forma sincrónica.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera el registro de llamadas entrantes y salientes para un dispositivo de conector de nube.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Detiene la generación del registro de llamadas entrantes y salientes para un dispositivo de conector de nube.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta el dispositivo en ejecución y cambia a un nuevo dispositivo recién implementado o de copia de seguridad.    <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala el dispositivo del conector de nube que se ejecuta desde el servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Anula el registro del equipo de conector de nube actual de un sitio RTC en la configuración de inquilinos en línea.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
   

