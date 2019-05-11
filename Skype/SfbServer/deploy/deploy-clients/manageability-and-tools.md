---
title: Administración y herramientas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
ms.openlocfilehash: 8a1d9f3e3d1c569a0473ca92cda6761ce63f0096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895036"
---
# <a name="skype-room-system-manageability-and-tools"></a>Administración y herramientas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
  
## <a name="administrative-portal"></a>Portal administrativo

Para Skype para las implementaciones locales de Business Server, puede usar el portal administrativo del sistema de salas de Skype para administrar y supervisar las implementaciones del sistema de salas de Skype dentro de la organización activamente.
  
Vea el siguiente artículo para obtener más detalles:
  
- [Implementar SRS v1 administrativas Web Portal en Skype para Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Sistema de sala de Skype se pueden supervisar a través de System Center Operations Manager (SCOM) descargando el [Paquete de administración del sistema de Skype sala](https://www.microsoft.com/download/details.aspx?id=42320) e instalar en el servidor de SCOM. Puede usar SCOM para establecer alertas, supervisar el estado del sistema de la sala de Skype, generar informes de tiempo de actividad y mucho más. Sistema de sala de Skype viene con un agente de supervisión preinstalado que se puede configurar para que apunte al servidor SCOM. Consulte la Guía de instalación proporcionada por el fabricante del sistema de salas de Skype para saber cómo configurar al agente de supervisión en el sistema de sala de Skype.
  
## <a name="exchange-checklist"></a>Lista de comprobación de Exchange

- Confirme que la Detección automática está configurada y que hay un REGISTRO DE A/CNAME DE DNS disponible para autodiscover.domain.com.
    
- Realice un ping de detección automática (p. ej. Ping Autodiscover.contoso.com).
    
- Pruebe su servicio de Detección automática con la Herramienta Analizador de conectividad de Microsoft. Elija la primera prueba, "no se puede iniciar sesión con Office Outlook".
    
- Si la sala de reuniones ya tiene un buzón de recursos, ampliar esta cuenta para el sistema de sala de Skype (secuencia de comandos de ejemplo en la parte inferior de la página).
    
## <a name="skype-for-business-checklist"></a>Skype para lista de comprobación de negocio

- Ejecute las siguientes herramientas:
    
  - Skype para profesionales Best Practices Analyzer     
  - Skype para la herramienta de análisis de mantenimiento de negocio (Excel)    
  - Skype para analizador de conectividad empresarial 32 bits o 64 bits
    
- Revise [la solución de problemas de nuevo de forma útil y herramientas de análisis para Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirme que tienen un Skype para el grupo de negocio y un servidor de Office Web Apps y pueden compartir unas diapositivas de PowerPoint mediante el Skype para clientes empresariales.
    
- Si la sala de reuniones ya tiene un buzón de recursos, habilitarla para Skype para la empresa.
    
- Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.
    
## <a name="network"></a>Red

- Asegúrese de que dispone de una conexión de red por cable para el sistema de sala de Skype.
    
- Leer la Guía de planeación de Skype para la empresa de red.
    
- Solicitar un Skype para evaluación de la red empresarial a un Skype para las compañías asociadas.
    
- Lea a través de los datos de rendimiento capturados en el Skype para la herramienta de análisis de mantenimiento de negocio (Excel).
    
- Ejecute la Herramienta de análisis de red.
    
- Ejecute la Herramienta de diagnóstico previa a llamadas.
    
## <a name="skype-room-system-security"></a>Seguridad del sistema de salas de Skype

Sistema de sala de Skype es un sistema incrustado que puede integrarse completamente en una implementación de Windows, mediante la Skype para el modelo de seguridad empresariales, administración de derechos y herramientas de administración como SCOM. Estas características incluyen lo siguiente:
  
- Un filtro de escritura para evitar escrituras en el disco en modo de usuario 
    
- Un bloqueador de aplicaciones para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en el modo de usuario.
    
  - No hay aplicaciones estándares o visores residen en el hardware del sistema de salas de Skype. Todo el contenido se representa a través de los protocolos HTTP o RDP.
    
  - El equipo ejecuta el sistema operativo Windows Embedded Standard 7. Los socios OEM proporcionan todo el hardware, incluidos los dispositivos.
    
  - Unión de dominio opcional a Active Directory Domain Services (AD DS), que permite la administración y el control de cuentas de seguridad locales.
    
- También puede administrar la cuenta de administrador local mediante el Skype para el centro de administración de negocio.
    
- Sistema de sala de Skype se actualiza a través de los procesos estándar de Microsoft Update.
    
- Sistema de sala de Skype se conecta con Skype para la empresa.
    
  - Skype para la empresa usa el cifrado de extremo a extremo y autorización para todos los modos de comunicación
    
  - Sistema de sala de Skype admite Skype para los estándares de seguridad y cumplimiento de normas empresariales. Para obtener más información, vea [Planear la seguridad en Skype para Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licencia

Compruebe que usa un KMS para activar software. Si es así, es posible que necesite comprobar o agregar el Skype para la clave KMS de cliente empresarial a ella. Si no utiliza KMS, a continuación, solicitar el volumen licencias clave para la Skype para clientes empresariales MAK.
  
## <a name="license-keys"></a>Claves de licencia

Sistema de sala de Skype se ejecuta el Skype para el cliente de escritorio empresarial en segundo plano. Si el sistema de sala de Skype es un miembro de dominio, descubre su KMS. (y si tiene la clave de KMS de licencias por volumen se activará automáticamente). Licencias por volumen también proporcionan una clave de MAK, escriba tal como se muestra xxxxx-xxxxx-xxxxx-xxxxx. (Necesita acceso a Internet para activar con MAK pero no KMS). Para obtener más información, vea Volume activation of Office 2013.
  
- Para escribir la clave MAK, vaya a configuración del OEM \> SRS Licensing Tool. Haga clic en Comprobar estado. Cuando el estado dice "no se activa el producto", escriba la clave.
    
- Si durante la activación se produce un error que dice, "' el servicio de licencias de Software informó que la clave de producto no es válida," a continuación, compruebe que:
    
  - La clave se ha escrito correctamente.
    
  - Que escribió el Skype para la clave MAK de negocio y no otra clave.
    
  - El sistema tiene acceso a Internet.
    
- Puede realizar la activación mediante teléfono, pero debe haber intentado la activación con la Herramienta de licencias de SRS antes. Para realizar la activación por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado breve). En el Asistente para la activación de Office, seleccione la activación por teléfono, llame a Microsoft y, a continuación, escriba el número de tipo long y escriba una respuesta.
    
## <a name="certificate-authority"></a>Entidad de certificación

Confirme que la Entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta HTTP incluida en la propiedad Lista de revocación de certificados.
  
Importar el archivo de certificado (.crt) para el sistema de sala de Skype si usa Skype para Business Server. Puede obtenerlo fácilmente del recurso compartido CertEnroll del servidor de la Entidad de certificación, o en la carpeta raíz de confianza de cualquier equipo unido al dominio.
  
## <a name="certificates"></a>Certificados

Compruebe que la Entidad de certificación tiene una ruta HTTP en la Lista de revocación de certificados. Si no es así, actualice su Entidad de certificación para que tenga una.
  
Instalar certificados en el programa de instalación de la administración del sistema de salón de Skype en configuración del sistema \> Administrador de certificados. Necesita la Entidad de certificación raíz de la empresa para su certificado interno.
  
Una forma de obtener los certificados que necesita es detectar la Entidad de certificación que emitió los certificados. Para Skype para Business Server, en un PC en Skype para la empresa, haga clic en configuración de \> herramientas \> configuración conferencia de acceso telefónico. Se abrirá una página web protegida por la entidad de certificación que ha emitido los certificados internos. Haga clic en el icono de candado en la barra de dirección del navegador para mostrar un informe de seguridad. Haga clic en Ver certificados y examine la propiedad Puntos de distribución CRL. El segundo parámetro de CN debería ser el nombre del servidor de la Entidad de certificación. Ahora abra el Explorador de Windows para esa dirección \\ \< el nombre del servidor de entidad emisora de certificados \>\CertEnroll. Copie los dos archivos .crl y el archivo .crt en una unidad extraíble y póngalos en la parte izquierda del panel SMART.
  
Importar el archivo .crt al sistema de salón de Skype en la carpeta de la entidad de certificación de salón de confianza.
  
Importar los archivos .crl en el sistema de sala de Skype en la carpeta de entidades de certificación intermedias. (Necesita cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).
  
Nota: El servidor de Office Web Apps 2013 puede compartir la misma entidad de certificación como Skype para la empresa. Si no lo hace, no podrá compartir archivos de PowerPoint durante una reunión. Póngase en contacto con el departamento de TI y obtenga los archivos CRT y CRL del CertEnroll del recurso compartido de red de la Entidad de certificación tal y como se ha explicado anteriormente. 
  
Puede simplificar la pertenencia al dominio algunas cosas debido a que el sistema de sala de Skype puede tratar como un sistema de Windows y puede depender de Active Directory para algunos de los aspectos de certificado. De todas formas, es mejor administrar esto manualmente.
  

