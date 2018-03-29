---
title: Administración y herramientas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a>Administración y herramientas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
  
## <a name="administrative-portal"></a>Portal administrativo

Para Skype para las implementaciones locales de Business Server, puede utilizar el portal de Skype sala sistema administrativo para administrar y supervisar la implementación del sistema de sala de Skype dentro de su organización activamente.
  
Vea los artículos siguientes para obtener más información:
  
- [Implementar el Portal de Web administrativa sistema de sala de Lync Lync Server 2013](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [Configurar el entorno de Lync Server 2013 para Lync sala sistema administrativo Portal Web](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [Instalación del Portal de administración Web de sistema de sala de Lync 2013 de Lync Server](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [Mediante el Portal de administración Web de sistema de sala de Lync 2013 de Lync Server](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Sistema de sala de Skype puede controlarse a través de System Center Operations Manager (SCOM) descargando el [Paquete de administración de sistema de sala de Skype](https://www.microsoft.com/en-us/download/details.aspx?id=42320) e instalarlo en el servidor SCOM. Puede utilizar SCOM para establecer alertas, supervisar el estado del sistema del sitio de Skype, generar informes de actividad y mucho más. Sistema de sala de Skype viene con un agente de supervisión preinstalado que puede configurarse para que apunte al servidor SCOM. Consulte la Guía de instalación proporcionada por el fabricante del sistema del sitio de Skype para saber cómo configurar al agente de supervisión en el sistema del sitio de Skype.
  
## <a name="exchange-checklist"></a>Lista de comprobación de Exchange

- Confirme que la Detección automática está configurada y que hay un REGISTRO DE A/CNAME DE DNS disponible para autodiscover.domain.com.
    
- Realice un ping de detección automática (p. ej. Ping Autodiscover.contoso.com).
    
- Pruebe su servicio de Detección automática con la Herramienta Analizador de conectividad de Microsoft. Elija la primera prueba, "Yo no puedo iniciar sesión con Office Outlook".
    
- Si la sala de reuniones ya tiene un buzón de recursos, ampliar esta cuenta para el sistema de sala de Skype (secuencia de comandos de ejemplo en la parte inferior de la página).
    
## <a name="skype-for-business-checklist"></a>Skype para lista de comprobación de negocio

- Ejecute las siguientes herramientas:
    
  - Skype para negocios Best Practices Analyzer 
    
  - Skype para la herramienta de análisis de negocio salud (Excel) 
    
  - Skype para el analizador de conectividad empresarial 32 bits o 64 bits
    
- Revise [la solución de problemas de nuevo de forma útil y herramientas de análisis para Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirme que tiene un Skype para el grupo de negocio y un servidor de Office Web Apps y puede compartir un deck de PowerPoint utilizando el Skype para el cliente de Business.
    
- Si la sala de reuniones ya tiene un buzón de recursos, habilitarla para Skype para el negocio.
    
- Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.
    
## <a name="network"></a>Red

- Asegúrese de que dispone de una conexión de red con cable para el sistema de sala de Skype.
    
- Lea la Guía de planeamiento para Skype para el negocio de red.
    
- Solicitar un Skype para la evaluación de la red empresarial desde un Skype para el socio comercial.
    
- Lea los datos de rendimiento capturados en el Skype para la herramienta de análisis de negocio salud (Excel).
    
- Ejecute la Herramienta de análisis de red.
    
- Ejecute la Herramienta de diagnóstico previa a llamadas.
    
## <a name="skype-room-system-security"></a>Seguridad del sistema de sala de Skype

Sistema de sala de Skype es un sistema incrustado que puede integrarse completamente en una implementación de Windows, usando el Skype para el modelo de seguridad de negocios, administración de derechos y herramientas de administración como SCOM. Estas características incluyen lo siguiente:
  
- Un filtro de escritura para evitar escrituras en el disco en modo de usuario 
    
- Un bloqueador de aplicaciones para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en el modo de usuario.
    
  - No hay aplicaciones estándares o visores residen en el hardware del sistema de sala de Skype. Todo el contenido se representa mediante los protocolos HTTP o RDP.
    
  - El equipo ejecuta el sistema operativo Windows Embedded Standard 7. Los socios OEM proporcionan todo el hardware, incluidos los dispositivos.
    
  - Unión de dominio opcional a Active Directory Domain Services (AD DS), que permite la administración y el control de cuentas de seguridad locales.
    
- También puede administrar la cuenta de administrador local mediante el Skype para el centro de administración de negocios.
    
- Sistema de sala de Skype se actualiza mediante los procesos estándar de Microsoft Update.
    
- Sistema de sala de Skype se conecta con Skype para el negocio.
    
  - Skype para empresas utiliza cifrado de extremo a extremo y la autorización para todos los modos de comunicación
    
  - Sistema de sala de Skype es compatible con Skype para los estándares de seguridad y cumplimiento de normas empresariales. Consulte Planear la seguridad en Lync Server 2013 para obtener más información.
    
## <a name="license"></a>Licencia

Compruebe que usa un KMS para activar software. Si es así, puede que necesite comprobar o agregar el Skype para la clave KMS cliente empresarial a él. Si no utiliza KMS, solicitar la clave de licencias por para el Skype para Business client MAK de volumen.
  
## <a name="license-keys"></a>Claves de licencia

Sistema de sala de Skype se ejecuta el Skype para el cliente de escritorio de negocios en el plano. Si el sistema del sitio de Skype es miembro de un dominio, descubrirá el KMS. (y si tiene la clave de Lync KMS de licencias por volumen se activará automáticamente). Licencias por volumen también proporciona una MAK, que se escribe como muestra xxxxx-xxxxx-xxxxx-xxxxx. (Necesita acceso a Internet para activarse utilizando MAK pero no KMS). Para obtener más información, vea activación por volumen de Office 2013.
  
- Para introducir la clave MAK, vaya a configuración del OEM \> SRS Licensing Tool. Haga clic en Comprobar estado. Cuando el estado dice "no se activa el producto", introduzca la clave.
    
- Si durante la activación se produce un error que dice: "' el servicio de licencias de Software informó que la clave del producto es válida," a continuación, compruebe que:
    
  - La clave se ha escrito correctamente.
    
  - Insertó el Skype de clave MAK de negocio y no en otro.
    
  - El sistema tiene acceso a Internet.
    
- Puede realizar la activación mediante teléfono, pero debe haber intentado la activación con la Herramienta de licencias de SRS antes. Para realizar la activación por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado breve). En el Asistente para la activación de Office, seleccione la activación por teléfono, llame a Microsoft, escriba el número de tipo long y escribir una respuesta.
    
## <a name="certificate-authority"></a>Entidad de certificación

Confirme que la Entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta HTTP incluida en la propiedad Lista de revocación de certificados.
  
Importar el archivo de certificado (.crt) al sistema de sala de Skype si utiliza Skype para Business Server. Puede obtenerlo fácilmente del recurso compartido CertEnroll del servidor de la Entidad de certificación, o en la carpeta raíz de confianza de cualquier equipo unido al dominio.
  
## <a name="certificates"></a>Certificados

Compruebe que la Entidad de certificación tiene una ruta HTTP en la Lista de revocación de certificados. Si no es así, actualice su Entidad de certificación para que tenga una.
  
Instalar los certificados en la configuración del administrador del sistema de sala de Skype en la configuración del sistema \> Administrador de certificados. Necesita la Entidad de certificación raíz de la empresa para su certificado interno.
  
Una forma de obtener los certificados que necesita es detectar la Entidad de certificación que emitió los certificados. Skype para Business Server, en un PC de Skype para el negocio, haga clic en configuración \> herramientas \> configuración conferencia de acceso telefónico. Esto abrirá una página web asegurada por la Entidad de certificación que emitió los certificados de Lync internos. Haga clic en el icono de candado en la barra de dirección del navegador para mostrar un informe de seguridad. Haga clic en Ver certificados y examine la propiedad Puntos de distribución CRL. El segundo parámetro de CN debería ser el nombre del servidor de la Entidad de certificación. Ahora abra el Explorador de Windows para esa dirección \\ \< nombre del servidor de entidad emisora de certificados \>\CertEnroll. Copie los dos archivos .crl y el archivo .crt en una unidad extraíble y póngalos en la parte izquierda del panel SMART.
  
Importar el archivo .crt al sistema de sala de Skype bajo carpeta de sala de confianza entidad emisora de certificados.
  
Importar los archivos .crl en el sistema de sala de Skype en la carpeta entidades emisoras de certificados intermedias. (Necesita cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).
  
Nota: El servidor de Office Web Apps 2013 puede compartir la misma Entidad de certificación que Lync. Si no lo hace, no podrá compartir archivos de PowerPoint durante una reunión. Póngase en contacto con el departamento de TI y obtenga los archivos CRT y CRL del CertEnroll del recurso compartido de red de la Entidad de certificación tal y como se ha explicado anteriormente. 
  
Pertenencia a un dominio puede simplificar algunas cosas porque el sistema de sala de Skype puede tratar como un sistema de Windows y puede depender de Active Directory para algunos de los aspectos del certificado. De todas formas, es mejor administrar esto manualmente.
  

