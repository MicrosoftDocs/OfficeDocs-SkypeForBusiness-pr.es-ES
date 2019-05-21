---
title: Administración y herramientas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293546"
---
# <a name="skype-room-system-manageability-and-tools"></a>Administración y herramientas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
  
## <a name="administrative-portal"></a>Portal administrativo

Para las implementaciones locales de Skype empresarial Server, puede usar el portal administrativo del sistema de salas de Skype para administrar y supervisar activamente las implementaciones de sistemas de salas de Skype dentro de su organización.
  
Para obtener más información, consulte el artículo siguiente:
  
- [Implementar el portal web administrativo SRS V1 en Skype empresarial Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

El sistema de salas de Skype se puede supervisar a través de System Center Operations Manager (SCOM) descargando el [módulo de administración de sistema de Skype Room](https://www.microsoft.com/download/details.aspx?id=42320) e instálelo en el servidor de SCOM. Puede usar SCOM para establecer alertas, supervisar el estado del sistema de salas de Skype, generar informes de tiempo de actividad y mucho más. El sistema de salas de Skype viene con un agente de supervisión preinstalado que se puede configurar para que apunte al servidor de SCOM. Consulte la guía de instalación proporcionada por el fabricante de su sistema de salas de Skype para saber cómo configurar el agente de supervisión en el sistema de salas de Skype.
  
## <a name="exchange-checklist"></a>Lista de comprobación de Exchange

- Confirme que la Detección automática está configurada y que hay un REGISTRO DE A/CNAME DE DNS disponible para autodiscover.domain.com.
    
- Realice un ping de detección automática (p. ej. Ping Autodiscover.contoso.com).
    
- Pruebe su servicio de Detección automática con la Herramienta Analizador de conectividad de Microsoft. Elija la primera prueba, "no puedo iniciar sesión con Office Outlook".
    
- Si la sala de reuniones ya tiene un buzón de recursos, extienda esta cuenta para el sistema de salas de Skype (secuencia de comandos de ejemplo en la parte inferior de la página).
    
## <a name="skype-for-business-checklist"></a>Lista de comprobación de Skype empresarial

- Ejecute las siguientes herramientas:
    
  - Analizador de procedimientos recomendados de Skype empresarial     
  - Herramienta de análisis de mantenimiento de Skype empresarial (Excel)    
  - Analizador de conectividad de Skype para empresas 32-bit o 64 bits
    
- Revise [nuevas herramientas de análisis y solución de problemas para Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirme que tiene un grupo de Skype empresarial y un servidor de Office Web Apps y que puede compartir un lote de PowerPoint con el cliente de Skype empresarial.
    
- Si la sala de reuniones ya tiene un buzón de recursos, habilítelo para Skype empresarial.
    
- Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.
    
## <a name="network"></a>Red

- Asegúrate de tener una conexión de red cableada para el sistema de salas de Skype.
    
- Lea la guía de planificación de redes para Skype empresarial.
    
- Solicite una evaluación de la red de Skype empresarial desde un socio de Skype empresarial.
    
- Lea los datos de rendimiento que se capturan en la herramienta de análisis de estado de Skype empresarial (Excel).
    
- Ejecute la Herramienta de análisis de red.
    
- Ejecute la Herramienta de diagnóstico previa a llamadas.
    
## <a name="skype-room-system-security"></a>Seguridad del sistema de salas de Skype

El sistema de salas de Skype es un sistema integrado que se puede integrar completamente en una implementación de Windows mediante el modelo de seguridad de Skype para empresas, la administración de derechos y las herramientas de administración, como SCOM. Estas características incluyen lo siguiente:
  
- Un filtro de escritura para evitar escrituras en el disco en modo de usuario 
    
- Un bloqueador de aplicaciones para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en el modo de usuario.
    
  - No hay aplicaciones ni visores estándar en el hardware del sistema de Skype Room. Todo el contenido se representa a través de protocolos HTTP o RDP.
    
  - El equipo ejecuta el sistema operativo Windows Embedded Standard 7. Los socios OEM proporcionan todo el hardware, incluidos los dispositivos.
    
  - Unión de dominio opcional a Active Directory Domain Services (AD DS), que permite la administración y el control de cuentas de seguridad locales.
    
- También puede administrar la cuenta de administrador local con el centro de administración de Skype empresarial.
    
- El sistema de salas de Skype se actualiza a través de los procesos estándar de Microsoft Update.
    
- El sistema de salas de Skype se conecta con Skype empresarial.
    
  - Skype empresarial usa el cifrado y la autorización end-to-end para todos los modos de comunicación
    
  - El sistema de salas de Skype es compatible con las normas de seguridad y cumplimiento de Skype empresarial. Para obtener más información, consulte [planear la seguridad en Skype empresarial Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licencia

Compruebe que usa un KMS para activar software. Si es así, es posible que tenga que comprobar o agregar la clave KMS del cliente de Skype empresarial. Si no usa KMS, solicite la clave de licencias por volumen para la MAK de cliente de Skype empresarial.
  
## <a name="license-keys"></a>Claves de licencia

El sistema de salas de Skype ejecuta el cliente de escritorio de Skype empresarial en segundo plano. Si el sistema de la sala de Skype es un miembro de dominio, detectará su KMS. (y si tiene la clave KMS de licencias por volumen, se activará automáticamente). Las licencias por volumen también proporcionan una MAK, que se especifica al mostrar xxxxx-xxxxx-xxxxx-xxxxx. (Necesita acceso a Internet para activarse mediante MAK, pero no KMS). Para obtener más información, consulte activación por volumen de Office 2013.
  
- Para introducir la clave MAK, vaya a configuración \> OEM herramienta de licencias de SRS. Haga clic en Comprobar estado. Cuando el estado indica "el producto no está activado", escribe la tecla.
    
- Si durante la activación recibe un error que dice "' el servicio de licencias de software notificó que la clave de producto no es válida", compruebe que:
    
  - La clave se ha escrito correctamente.
    
  - Introdujo la clave MAK de Skype empresarial y no otra tecla.
    
  - El sistema tiene acceso a Internet.
    
- Puede realizar la activación mediante teléfono, pero debe haber intentado la activación con la Herramienta de licencias de SRS antes. Para realizar la activación por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado breve). En el Asistente para la activación de Office, seleccione activación por teléfono, llamar a Microsoft, escriba el número largo y escriba una respuesta.
    
## <a name="certificate-authority"></a>Entidad de certificación

Confirme que la Entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta HTTP incluida en la propiedad Lista de revocación de certificados.
  
Si usas Skype empresarial Server, importa el archivo de certificados (. CRT) al sistema de salas de Skype. Puede obtenerlo fácilmente del recurso compartido CertEnroll del servidor de la Entidad de certificación, o en la carpeta raíz de confianza de cualquier equipo unido al dominio.
  
## <a name="certificates"></a>Certificados

Compruebe que la Entidad de certificación tiene una ruta HTTP en la Lista de revocación de certificados. Si no es así, actualice su Entidad de certificación para que tenga una.
  
Instale certificados en la configuración del administrador del sistema de salas de Skype en \> el administrador de certificados de configuración del sistema. Necesita la Entidad de certificación raíz de la empresa para su certificado interno.
  
Una forma de obtener los certificados que necesita es detectar la Entidad de certificación que emitió los certificados. Para Skype empresarial Server, en un equipo PC en Skype empresarial, haga clic en \> configuración \> herramientas de conferencia de acceso telefónico local. Se abrirá una página web asegurada por la entidad emisora que emitió los certificados internos. Haga clic en el icono de candado en la barra de dirección del navegador para mostrar un informe de seguridad. Haga clic en Ver certificados y examine la propiedad Puntos de distribución CRL. El segundo parámetro de CN debería ser el nombre del servidor de la Entidad de certificación. Ahora abra el explorador de Windows para \\ \< esa dirección nombre \>de servidor CA \CertEnroll. Copie los dos archivos .crl y el archivo .crt en una unidad extraíble y póngalos en la parte izquierda del panel SMART.
  
Importe el archivo. CRT a la carpeta de la entidad emisora de certificados de confianza en el sistema de salas de Skype.
  
Importe los archivos. CRL en el sistema de salas de Skype en la carpeta entidades emisoras de certificados intermedias. (Necesita cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).
  
Nota: el servidor de Office Web Apps 2013 puede compartir la misma CA como Skype empresarial. Si no lo hace, no podrá compartir archivos de PowerPoint durante una reunión. Póngase en contacto con el departamento de TI y obtenga los archivos CRT y CRL del CertEnroll del recurso compartido de red de la Entidad de certificación tal y como se ha explicado anteriormente. 
  
La pertenencia a dominios puede simplificar algunas cosas porque puede tratar el sistema de salas de Skype como sistema Windows y puede confiar en Active Directory para algunos de los aspectos de los certificados. De todas formas, es mejor administrar esto manualmente.
  

