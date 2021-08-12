---
title: Skype Herramientas y capacidad de administración del sistema de sala
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información sobre las herramientas de administración para Skype Room System.
ms.openlocfilehash: cdf7430ecc155526cc560832f58f00a6119ce8ab8e777bbb592cba205c0407f9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310079"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Herramientas y capacidad de administración del sistema de sala
 
Lea este tema para obtener información sobre las herramientas de administración para Skype Room System.
  
## <a name="administrative-portal"></a>Portal administrativo

Para Skype Empresarial Server implementaciones locales, puede usar el portal administrativo del sistema de sala de Skype para administrar y supervisar activamente las implementaciones del sistema de sala Skype dentro de la organización.
  
Vea el siguiente artículo para obtener más detalles:
  
- [Implementar SRS v1 Administrative Web Portal en Skype Empresarial Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange Lista de comprobación

- Confirme que la detección automática está configurada y que hay disponible un REGISTRO A/CNAME de DNS interno para autodiscover.domain.com.
    
- Ping autodiscover (por ejemplo, Ping Autodiscover.contoso.com).
    
- Pruebe el servicio de detección automática con la herramienta Analizador de conectividad de Microsoft. Elija la primera prueba: "No puedo iniciar sesión con Office Outlook".
    
- Si la sala de reuniones ya tiene un buzón de recursos, extienda esta cuenta para el sistema de salas Skype (script de ejemplo en la parte inferior de la página).
    
## <a name="skype-for-business-checklist"></a>Skype Empresarial Lista de comprobación

- Ejecute las siguientes herramientas:
    
  - Skype Empresarial Analizador de procedimientos recomendados     
  - Skype Empresarial Herramienta de análisis de estado (Excel)    
  - Skype Empresarial Analizador de conectividad de 32 o 64 bits
    
- Revise [Útiles nuevas herramientas de solución de problemas y](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)análisis para Office 365 . Confirme que tiene un grupo Skype Empresarial de servidores y un servidor Office Web Apps y puede compartir una PowerPoint con el Skype Empresarial cliente.
    
- Si la sala de reuniones ya tiene un buzón de recursos, habilitelo para Skype Empresarial.
    
- Si es necesario, solicite un DID (número de teléfono) para el sistema Sala de reuniones y actualice el campo Teléfono general en la herramienta Active Directory.
    
## <a name="network"></a>Red

- Asegúrese de que tiene una conexión de red por cable para el Skype room system.
    
- Lea la Guía de planeación de red Skype Empresarial.
    
- Solicite una evaluación Skype Empresarial de red de un Skype Empresarial asociado.
    
- Lea los datos de rendimiento capturados en Skype Empresarial Health Analysis Tool (Excel).
    
- Ejecute la Herramienta de análisis de red.
    
- Ejecute la Herramienta de diagnóstico de llamadas previas.
    
## <a name="skype-room-system-security"></a>Skype Seguridad del sistema de sala

Skype Room System es un sistema incrustado que se puede integrar completamente en una implementación de Windows, mediante el modelo de seguridad Skype Empresarial, la administración de derechos y las herramientas de administración, como SCOM. Entre las características se incluyen:
  
- Un filtro de escritura para evitar escrituras en disco en modo de usuario 
    
- App Locker para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en modo de usuario.
    
  - No hay aplicaciones ni visores estándar en el hardware Skype sistema de sala. Todo el contenido se representa a través de protocolos HTTP o RDP.
    
  - El equipo del dispositivo ejecuta el Windows operativo Embedded Standard 7. Todo el hardware, incluidos los dispositivos, lo proporcionan los partners OEM.
    
  - Combinación de dominio opcional a servicios de dominio de Active Directory (AD DS), lo que habilita la administración y el control de cuentas de seguridad local.
    
- También puede administrar la cuenta de administrador local mediante el centro Skype Empresarial administración.
    
- Skype El sistema de sala se actualiza mediante procesos estándar de Microsoft Update.
    
- Skype El sistema de sala se conecta Skype Empresarial.
    
  - Skype Empresarial usa cifrado y autorización de extremo a extremo para todos los modos de comunicación
    
  - Skype Room System admite Skype Empresarial seguridad y cumplimiento normativo. Vea [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obtener más información.
    
## <a name="license"></a>Licencia

Compruebe que usa un KMS para activar software. Si es así, es posible que deba comprobar o agregar la Skype Empresarial cliente KMS clave. Si no está usando KMS, solicite la clave de licencia por volumen para la MAK Skype Empresarial cliente.
  
## <a name="license-keys"></a>Claves de licencia

Skype Room System ejecuta el Skype Empresarial de escritorio en segundo plano. Si Skype room system es un miembro de dominio, descubrirá su KMS. (y si tiene la clave de licencia por volumen KMS se activará automáticamente). Las licencias por volumen también proporcionan una MAK, que se especifica ya que muestra xxxxx-xxxxx-xxxxx-xxxxx. (Necesita acceso a Internet para activarse con MAK, pero no KMS). Para obtener más información, vea Activación por volumen de Office 2013.
  
- Para escribir la clave MAK, vaya a OEM Configuración \> herramienta de licencias SRS. Haga clic en Comprobar estado. Cuando el estado diga "el producto no está activado", escriba la clave.
    
- Si durante la activación se produce un error que indica: "'El servicio de licencias de software informó de que la clave del producto no es válida", compruebe que:
    
  - La clave se introdujo correctamente.
    
  - Ha escrito la Skype Empresarial MAK y no otra clave.
    
  - El sistema tiene acceso a Internet.
    
- Puede activarse por teléfono, pero debe haber intentado activarla primero con la herramienta de licencias SRS. Para activarla por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado corta). En el Office de activación, seleccione Activación telefónica, llame a Microsoft, escriba el número largo y escriba una respuesta.
    
## <a name="certificate-authority"></a>Entidad de certificación

Confirme que la entidad de certificación usada para emitir el certificado Office Web Apps Server 2013 tiene una ruta de acceso HTTP incluida en la propiedad Lista de revocación de certificados.
  
Importe el archivo de certificado (.crt) al Skype room system si usa Skype Empresarial Server. Se obtiene fácilmente desde el recurso compartido CertEnroll del servidor de ca o en la carpeta Raíz de confianza de cualquier equipo unido a un dominio.
  
## <a name="certificates"></a>Certificados

Compruebe que la entidad de certificación tiene una ruta de acceso http para la lista de revocación de certificados. Si no es así, actualice la CA para que incluya una.
  
Instale certificados en la configuración de administración del Skype room system en System Configuración \> Certificate Manager. Necesita la ca raíz Enterprise para el certificado interno.
  
Una forma de obtener los certificados que necesita es detectar la CA que emitió los certificados. Para Skype Empresarial Server, en un equipo de Skype Empresarial, haga clic en Configuración Herramientas de acceso telefónico \> \> Configuración. Se abre una página web protegida por la CA que emitió los certificados internos. Haga clic en el icono Bloquear de la barra de direcciones del explorador para mostrar un informe de seguridad. Haga clic en Ver certificados y examine la propiedad Punto de distribución CRL. El segundo parámetro CN debe ser el nombre del servidor de la CA. Ahora abra Windows Explorer para esa \\ \< CA Server Name \> dirección \CertEnroll. Copie los dos archivos .crl y el archivo .crt en una unidad flash y póngalo en el lado izquierdo de la tarjeta SMART.
  
Importe el archivo .crt al sistema de Skype en la carpeta Entidad de certificación de sala de confianza.
  
Importe los archivos .crl en el Skype room system en la carpeta Autoridades de certificado intermedias. (Debe cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).
  
Nota: El servidor Office Web Apps 2013 puede compartir la misma CA que Skype Empresarial. Si no es así, no podrá compartir PowerPoint en una reunión. Compruebe con IT y obtenga los archivos CRT y CRL de certEnroll del recurso compartido de red de ca, tal como se ha explicado anteriormente. 
  
La pertenencia a dominios puede simplificar algunas cosas porque puede tratar el sistema de sala de Skype como un sistema Windows y puede depender de Active Directory para algunos de los aspectos del certificado. Sin embargo, lo mejor es administrarlo manualmente.
