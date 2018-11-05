---
title: "Lync Server 2013 : Autres prises en charge et conf. de serveur requises"
TOCTitle: Compatibilidad y requisitos para un servidor adicional
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48275719
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad y requisitos para un servidor adicional en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Además de la compatibilidad de software descrita en otras secciones de esta documentación sobre compatibilidad, Lync Server 2013 presenta las siguientes limitaciones de compatibilidad:

  - Lync Server 2013 admite el equilibrio de carga de sistema de nombres de dominio (DNS) y de hardware para roles de servidor específicos. También admite, si corresponde, el equilibrio de carga de aplicaciones para servidores de mediación. Para obtener información detallada acerca de cuándo usar cada uno de ellos, consulte la documentación referente a la planeación.

  - Lync Server 2013 usa el protocolo de expansión de la lista de distribución (DLX) para expandir listas de distribución. Este protocolo también especifica el método de servicio web que se usa para obtener la pertenencia de una lista de distribución. Microsoft Exchange Server admite grupos dinámicos que no tengan asignado estáticamente ningún miembro. En lugar de ello, almacenan consultas que se evalúan al expandir el grupo. DLX no es compatible con listas de distribución dinámicas.

  - El Asistente para habilitar usuarios no permite la conversión automática de caracteres que no sean ingleses a un URI compatible con SIP, por lo que la dirección SIP debe modificarse manualmente.

  - Para servidores que ejecuten software antivirus, consulte las exclusiones de virus y otras recomendaciones sobre seguridad en [Exclusiones de la detección de virus para Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md).

  - Si usa IPsec, se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para más información, consulte [Excepciones de IPsec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación referente a la planeación.

  - Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente. Para más información acerca de la implementación de QoS, consulte [Administración de la Calidad de servicio (QoS) en Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) en la documentación referente a las operaciones.

  - Se admite el uso del firewall del sistema operativo. Lync Server 2013 administra excepciones del firewall del sistema operativo, excepto para el software de base de datos Microsoft SQL Server. Para más información acerca de firewall de los requisitos de SQL Server, consulte la documentación de SQL Server.

  - Las interfaces externas que se usan para permitir el acceso de usuarios externos deben estar en una subred independiente, *no* en la misma red que las interfaces internas.

  - La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.

  - Ahora, tras la publicación de las Actualizaciones acumulativas de Lync Server 2013: julio de 2013, Lync Server 2013 admite la autenticación en dos fases. Para más información, vea [Planeación e implementación de la autenticación en dos fases en Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La mayoría de servidores internos requieren un tipo de certificado definido como **Open Authentication** (OAuth). Durante la fase **Solicitar, instalar o asignar certificados** del Asistente para la implementación de Lync Server, se le pedirá que solicite y asigne un certificado OAuth. El tamaño mínimo de una clave de certificado OAuth son 1024 bits. Puede que aparezca una advertencia si solicita un certificado con una longitud menor de 2048 bits. Para evitar los problemas que podrían surgir en el caso de que no aparezca ninguna advertencia y se introduzca una clave con una longitud mayor de 2048 bits, se recomienda encarecidamente utilizar siempre una longitud de clave de 2048 para los certificados OAuth.

  - Lync Server 2013 y Microsoft Exchange Server 2010 Service Pack 1 (SP1) funcionan con compatibilidad con algoritmos del Estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos de Windows Server 2008 R2 se configuran para usar algoritmos FIPS 140-2 para la criptografía del sistema. Para implementar la compatibilidad con FIPS, hay que configurar cada uno de los servidores que ejecutan Lync Server 2013. Para más información sobre los algoritmos compatibles con FIPS y sobre cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge Base “Criptografía de sistema: Usar algoritmos compatibles con FIPS para cifrado, hash y configuración de seguridad de firma en Windows XP y en versiones posteriores de Windows” en [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Para más información sobre la compatibilidad con FIPS 140-2 y las limitaciones en Exchange 2010, consulte el artículo sobre Exchange 2010 SP1 y compatibilidad con algoritmos compatibles con FIPS en <http://go.microsoft.com/fwlink/?linkid=205335>.

Lync Server 2013 precisa la instalación de otro software en componentes específicos antes o durante la implementación. Estos incluyen software disponible con el sistema operativo, software que se puede descargar y software que se instala automáticamente durante la instalación de Lync Server 2013. A continuación se muestra una lista del software adicional que puede ser necesario:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Paquete redistribuible de Microsoft Visual C++ 2012
    

    > [!NOTE]
    > El paquete redistribuible de Microsoft Visual C++ 2012 se instala automáticamente con la instalación de Lync Server 2013. No instale ni use otras versiones.



  - Paquete redistribuible del Módulo URL Rewrite versión 2.0

  - Motor en tiempo de ejecución de Windows Media Format

  - Windows PowerShell versión 2.0

  - Complemento del explorador Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la última versión para el panel de control de Lync Server)

  - Herramientas de Servicios de dominio de Active Directory

Algunos de estos requisitos de software se aplican solamente a roles de servidor o componentes específicos. Para más información acerca de estos requisitos de software, consulte [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.

