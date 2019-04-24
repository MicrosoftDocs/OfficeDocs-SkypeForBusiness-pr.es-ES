---
title: Referencia de cmdlets de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: En la siguiente tabla se muestran los cmdlets de Skype Empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
ms.openlocfilehash: aa8b8ebe4ffd7d1cb2c405eae5fe6604c5f4c378
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234264"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
En la siguiente tabla se muestran los cmdlets de Skype Empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
  
> [!NOTE]
> Debe ejecutar todos los cmdlets en el equipo host de conector en la nube, y debe ejecutar la sesión de PowerShell como administrador. 
  
|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versión 1.4.2 y posteriores  <br/> |Crea una copia de seguridad del servicio de la entidad de certificación en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Cloud Connector.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara el servidor de host de conector en la nube para el proceso de actualización al poner en modo de mantenimiento. El dispositivo se "vacía"; es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Salidas actualización el modo de mantenimiento en el servidor de host de conector en la nube.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exporta una configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta un archivo de configuración de ejemplo de conector en la nube (. ini) en el directorio de dispositivo de un dispositivo de conector en la nube. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versión 1.4.2 y posteriores   <br/> |Exporta el certificado de entidad de certificación raíz en un archivo local en el servidor de host de conector en la nube.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera el directorio de trabajo en el servidor de host de conector en la nube. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Muestra el directorio actual donde se almacenan los registros de un dispositivo de conector en la nube..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versión 2.1 y versiones posterior  <br/> |Proporciona información de diagnóstico para el dispositivo de conector en la nube.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Devuelve la credencial de la implementación actual de conector en la nube.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Devuelve la ruta de acceso del archivo de certificado externo para la implementación de conector en la nube. El usuario debe preparar este certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene los archivos de instalación bases VHD y el conector de la nube. Esta carpeta se debe compartir con todos los demás equipos de un sitio de conector en la nube.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Muestra el directorio actual donde se almacenan los registros de nivel de sitio de conector en la nube.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versión 2.0 y posteriores  <br/> |Devuelve la versión en la instancia de Cloud Connector. Get-CCVersion solo se puede usar en la máquina host de Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versión 2.0 y posteriores  <br/> |Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector en la nube.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala el dispositivo conector en la nube: incluidos AD, almacén de Administración Central, el servidor de mediación y el servidor perimetral de máquinas virtuales, en el servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtiene información de alta disponibilidad de la configuración de inquilino en línea y se publica en el dispositivo de conector en la nube en el servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Un dispositivo debe estar registrado antes de se puede implementar y administrado por el servicio de administración de conector en la nube. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita el archivo de copia de seguridad del servicio de autoridad de certificación "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido de sitio para el conector en la nube.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita los certificados de servidores heredados del Almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo la versión 1.4.2  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo la versión 1.4.2  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Restablece los servidores de la entidad de certificación para instalar un nuevo certificado de entidad de certificación.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versión 2.1 y versiones posterior  <br/> |Limpia las credenciales y le pregunta si desea volver a escribir todas las credenciales usadas para la implementación actual de conector en la nube.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Las búsquedas de los registros de la llamada entrante y saliente en el directorio de registro de dispositivo de conector en la nube  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Establece el directorio de trabajo en el servidor de host de conector en la nube. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Establece las credenciales de la implementación actual de conector en la nube.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para el conector en la nube. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Descargas de forma sincrónica los bits de conector en la nube y el archivo msi.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera el registro de llamadas entrantes y salientes para un dispositivo de conector en la nube.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Registro de llamadas deja de generar el entrante y saliente para un dispositivo de conector en la nube.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta el dispositivo en ejecución y cambia a un nuevo dispositivo recién implementado o de copia de seguridad.    <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala el dispositivo conector en la nube que se está ejecutando desde el servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Elimina del registro el dispositivo actual de conector en la nube desde un sitio de RTC en la configuración del inquilino en línea.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
   

