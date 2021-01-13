---
title: Herramientas y capacidad de administración del Sistema de sala de Skype
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
description: Lea este tema para obtener información sobre las herramientas de administración del Sistema de sala de Skype.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805800"
---
# <a name="skype-room-system-manageability-and-tools"></a>Herramientas y capacidad de administración del Sistema de sala de Skype
 
Lea este tema para obtener información sobre las herramientas de administración del Sistema de sala de Skype.
  
## <a name="administrative-portal"></a>Portal administrativo

Para las implementaciones locales de Skype Empresarial Server, puede usar el portal administrativo del Sistema de sala de Skype para administrar y supervisar activamente las implementaciones del Sistema de sala de Skype en su organización.
  
Vea el siguiente artículo para obtener más información:
  
- [Implementar el portal web administrativo de SRS v1 en Skype Empresarial Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Lista de comprobación de Exchange

- Confirme que la detección automática está configurada y que hay disponible un REGISTRO A/CNAME de DNS interno para autodiscover.domain.com.
    
- Ping autodiscover (por ejemplo, Ping Autodiscover.contoso.com).
    
- Pruebe el servicio de detección automática con la herramienta Analizador de conectividad de Microsoft. Elija la primera prueba: "No puedo iniciar sesión con Office Outlook".
    
- Si la sala de reuniones ya tiene un buzón de recursos, extienda esta cuenta para el Sistema de salas de Skype (script de ejemplo en la parte inferior de la página).
    
## <a name="skype-for-business-checklist"></a>Lista de comprobación de Skype Empresarial

- Ejecute las siguientes herramientas:
    
  - Analizador de procedimientos recomendados de Skype Empresarial     
  - Herramienta de análisis de estado de Skype Empresarial (Excel)    
  - Analizador de conectividad de Skype Empresarial de 32 o 64 bits
    
- Revise [las nuevas herramientas de solución de problemas y análisis útiles para Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/) Confirme que tiene un grupo de Skype Empresarial y un servidor de Office Web Apps y puede compartir una presentación de PowerPoint con el cliente de Skype Empresarial.
    
- Si la sala de reuniones ya tiene un buzón de recursos, habilitelo para Skype Empresarial.
    
- Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.
    
## <a name="network"></a>Red

- Asegúrese de que tiene una conexión de red cableada para el Sistema de sala de Skype.
    
- Lea la Guía de planeación de red para Skype Empresarial.
    
- Solicitar una evaluación de red de Skype Empresarial a un partner de Skype Empresarial.
    
- Lea los datos de rendimiento capturados en la Herramienta de análisis de estado de Skype Empresarial (Excel).
    
- Ejecute la Herramienta de análisis de red.
    
- Ejecute la herramienta de diagnóstico previo a la llamada.
    
## <a name="skype-room-system-security"></a>Seguridad del sistema de sala de Skype

Sistema de sala de Skype es un sistema integrado que se puede integrar completamente en una implementación de Windows, mediante el modelo de seguridad de Skype Empresarial, la administración de derechos y las herramientas de administración como SCOM. Entre las características se incluyen:
  
- Un filtro de escritura para evitar escrituras en disco en modo de usuario 
    
- App Locker para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en modo de usuario.
    
  - No hay ninguna aplicación o visor estándar en el hardware del Sistema de sala de Skype. Todo el contenido se representa a través de protocolos HTTP o RDP.
    
  - El equipo del dispositivo ejecuta el sistema operativo Windows Embedded Standard 7. Todo el hardware, incluidos los dispositivos, lo proporcionan los partners OEM.
    
  - Unión de dominio opcional a Servicios de dominio de Active Directory (AD DS), lo que habilita la administración y el control de cuentas de seguridad local.
    
- También puede administrar la cuenta de administrador local mediante el Centro de administración de Skype Empresarial.
    
- El Sistema de sala de Skype se actualiza a través de procesos estándar de Microsoft Update.
    
- El Sistema de sala de Skype se conecta con Skype Empresarial.
    
  - Skype Empresarial usa cifrado y autorización de un extremo a otro para todos los modos de comunicación
    
  - El Sistema de sala de Skype es compatible con los estándares de seguridad y cumplimiento de Skype Empresarial. Consulte [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obtener más información.
    
## <a name="license"></a>Licencia

Comprueba que usas un KMS para activar software. Si es así, es posible que tenga que comprobar o agregarle la clave KMS del cliente de Skype Empresarial. Si no usa KMS, solicite la clave de licencia por volumen para la MAK del cliente de Skype Empresarial.
  
## <a name="license-keys"></a>Claves de licencia

El Sistema de sala de Skype ejecuta el cliente de escritorio de Skype Empresarial en segundo plano. Si El Sistema de sala de Skype es un miembro del dominio, detectará su KMS. (y si tiene la clave KMS de licencias por volumen, se activará automáticamente). Licencias por volumen también proporciona una MAK, que se especifica cuando se muestra xxxxx-xxxxx-xxxxx-xxxxx. (Necesitas acceso a Internet para activar con MAK, pero no con KMS). Para obtener más información, consulte Activación por volumen de Office 2013.
  
- Para escribir la clave MAK, vaya a La herramienta de licencias SRS de configuración \> de OEM. Haga clic en Comprobar estado. Cuando el estado indique "el producto no está activado", escriba la clave.
    
- Si durante la activación recibe un error que dice: "'El servicio de licencias de software informó de que la clave del producto no es válida", compruebe que:
    
  - La clave se introdujo correctamente.
    
  - Introdujo la clave MAK de Skype Empresarial y no otra clave.
    
  - El sistema tiene acceso a Internet.
    
- Puede activar por teléfono, pero debe haber intentado activar primero con la Herramienta de licencias de SRS. Para activarla por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado corta). En el Asistente para activación de Office, seleccione Activación telefónica, llame a Microsoft, escriba el número largo y escriba una respuesta.
    
## <a name="certificate-authority"></a>Entidad de certificación

Confirme que la entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta http incluida en la propiedad Lista de revocación de certificados.
  
Importe el archivo de certificado (.crt) al Sistema de sala de Skype si usa Skype Empresarial Server. Se obtiene fácilmente desde el recurso compartido CertEnroll del servidor de ca o en la carpeta raíz de confianza de cualquier equipo unido a un dominio.
  
## <a name="certificates"></a>Certificados

Compruebe que la entidad de certificación tiene una ruta http para la lista de revocación de certificados. Si no es así, actualice la ENTIDAD de certificación para incluir una.
  
Instale los certificados en la configuración de administración del Sistema de sala de Skype en el Administrador de certificados \> de configuración del sistema. Necesita la CA raíz de empresa para el certificado interno.
  
Una forma de obtener los certificados que necesita es descubrir la CA que emitió los certificados. For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings. Se abrirá una página web protegida por la CA que emitió los certificados internos. Haga clic en el icono de bloqueo de la barra de direcciones del explorador para mostrar un informe de seguridad. Haga clic en Ver certificados y examine la propiedad Punto de distribución CRL. El segundo parámetro CN debe ser el nombre del servidor de la CA. Ahora abra el Explorador de Windows para esa \\ \< CA Server Name \> dirección \CertEnroll. Copie los dos archivos .crl y el archivo .crt en una unidad flash y póngalo en el lado izquierdo del panel SMART.
  
Importe el archivo .crt al Sistema de sala de Skype en la carpeta Entidad de certificación de sala de confianza.
  
Importe los archivos .crl en el Sistema de sala de Skype en la carpeta De autoridades de certificado intermedias. (Debe cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).
  
Nota: El servidor de Office Web Apps 2013 puede compartir la misma CA que Skype Empresarial. Si no es así, no podrá compartir PowerPoint en una reunión. Consulte con EL Y obtenga los archivos CRT y CRL del certEnroll del recurso compartido de red de CA, como se explicó anteriormente. 
  
La pertenencia a un dominio puede simplificar algunas cosas porque puede tratar el Sistema de sala de Skype como un sistema de Windows y puede depender de Active Directory para algunos de los aspectos del certificado. Sin embargo, es mejor administrarlo manualmente.
  

