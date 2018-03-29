---
title: Referencia de cmdlets de Cloud Connector
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
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Referencia de cmdlets de Cloud Connector
 
En la siguiente tabla se muestran los cmdlets de Skype Empresarial Cloud Connector Edition con una breve descripción y vínculos a más información.
  
> [!NOTE]
> Debe ejecutar todos los cmdlets en la máquina host de Cloud Connector y deje ejecutar la sesión de PowerShell como administrador. 
  
|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Copia de seguridad CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versión 1.4.2 y posteriores  <br/> |Crea una copia de seguridad del servicio de la entidad de certificación en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.      <br/> |
|[Convertir CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Cloud Connector.   <br/> |
|[Escriba-CcUpdate](enter-ccupdate.md) <br/> |Prepara el servidor host de Cloud Connector para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo se "vacía"; es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.  <br/> |
|[Salir CcUpdate](exit-ccupdate.md) <br/> |Sale de la actualización del modo de mantenimiento en el servidor host de Cloud Connector.    <br/> |
|[CcConfiguration de exportación](export-ccconfiguration.md) <br/> |  Exporta una configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition. <br/> |
|[CcConfigurationSampleFile de exportación](export-ccconfigurationsamplefile.md) <br/> |Exporta un archivo de configuración de ejemplo de nube de conector (. ini) en el directorio del dispositivo de un dispositivo conector de nube. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.  <br/> |
|[CcRootCertificate de exportación](export-ccrootcertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Exporta un certificado de entidad de certificación raíz a un archivo local en el servidor host de Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera el directorio de trabajo del servidor host de Cloud Connector. Todos los archivos de implementación se almacenan en este directorio.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Muestra el directorio actual donde se almacenan los registros para un dispositivo conector de nube..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versión 2.1 y posteriores  <br/> |Proporciona información de diagnóstico del dispositivo conector de nube.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Devuelve las credenciales de la implementación de Cloud Connector existente.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Devuelve la ruta de acceso del archivo de certificados externos de la implementación de Cloud Connector. El usuario debe preparar este certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene los archivos de instalación de VHD y nube de conector de base. Esta carpeta debe compartirse con todos los otros equipos de un sitio de conector de nube.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Muestra el directorio actual donde se almacenan los registros de nivel de sitio para el conector de la nube.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versión 2.0 y posteriores  <br/> |Devuelve la versión en la instancia de Cloud Connector. Get-CCVersion solo se puede usar en la máquina host de Cloud Connector.  <br/> |
|[CcConfiguration de importación](import-ccconfiguration.md) <br/> Versión 2.0 y posteriores  <br/> |Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector de nube.  <br/> |
|[Instalar CcAppliance](install-ccappliance.md) <br/> |Instala el dispositivo conector de nube, incluyendo el anuncio, máquinas virtuales de servidor perimetral, servidor de mediación y almacén de Administración Central, en el servidor host.  <br/> |
|[CcAppliance publicar](publish-ccappliance.md) <br/> | Obtiene información de alta disponibilidad de la configuración de clientes en línea y los publica en el aparato de nube de conector en el servidor host. <br/> |
|[Registro CcAppliance](register-ccappliance.md) <br/> | Registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Un dispositivo debe estar registrado antes de que se pueda implementar y administrado por el servicio de administración del conector de la nube. <br/> |
|[Quitar CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita el archivo de copia de seguridad de servicio de autoridad de certificación "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio para el conector de la nube.  <br/> |
|[Quitar CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Quita los certificados de servidores heredados del Almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.  <br/> |
|[CcCACertificate renovar](renew-cccacertificate.md) <br/> Solo la versión 1.4.2  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[CcServerCertificate renovar](renew-ccservercertificate.md) <br/> Solo la versión 1.4.2  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
|[Restablecer CcCACertificate](reset-cccacertificate.md) <br/> Versión 1.4.2 y posteriores  <br/> |Restablece los servidores de la entidad de certificación para instalar un nuevo certificado de entidad de certificación.  <br/> |
|[Restauración CcCredentials](restore-cccredentials.md) <br/> Versión 2.1 y posteriores  <br/> |Limpia las credenciales y le pregunta si desea volver a escribir todas las credenciales utilizadas para la implementación de nube conector actual.  <br/> |
|[Búsqueda CcLog](search-cclog.md) <br/> |Busca los registros de llamadas entrantes y salientes en el directorio de registro de aplicaciones de Cloud Connector.  <br/> |
|[Conjunto de CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Establece el directorio de trabajo en el servidor de host de la nube de conector. Todos los archivos de implementación se almacenan en este directorio.  <br/> |
|[Conjunto de CcCredential](set-cccredential.md) <br/> |Establece las credenciales de la implementación de Cloud Connector existente.  <br/> |
|[Conjunto de CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.  <br/> |
|[Conjunto de CcSiteDirectory](set-ccsitedirectory.md) <br/> |Establece el directorio en el que se almacenarán los archivos de configuración a nivel de sitio para Cloud Connector. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.  <br/> |
|[Inicio CcDownload](start-ccdownload.md) <br/> |Descarga los bits de la nube de conector y el archivo msi de forma sincrónica.  <br/> |
|[Inicio CcLogging](start-cclogging.md) <br/> |Genera el registro de llamadas entrantes y salientes de un dispositivo conector de nube.  <br/> |
|[Parada CcLogging](stop-cclogging.md) <br/> |Registro de llamadas deja de generar el entrante y saliente para un dispositivo conector de nube.  <br/> |
|[Conmutador CcVersion](switch-ccversion.md) <br/> |Desconecta el dispositivo en ejecución y cambia a un nuevo dispositivo recién implementado o de copia de seguridad.    <br/> |
|[CcAppliance desinstalar](uninstall-ccappliance.md) <br/> |Desinstala el dispositivo conector de nube ejecución desde el servidor host.  <br/> |
|[Anular el registro de CcAppliance](unregister-ccappliance.md) <br/> |Elimina del registro el dispositivo conector de nube actual desde un sitio de RTC en la configuración de clientes en línea.  <br/> |
|[Actualización CcCACertificate](update-cccacertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Reinstala el servidor de AD del Servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz.  <br/> |
|[Actualización CcServerCertificate](update-ccservercertificate.md) <br/> Versión 2.0 y posteriores  <br/> |Renueva los certificados de Cloud Connector cuando están a punto de expirar o ya han expirado.  <br/> |
   

