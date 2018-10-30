---
title: Características clave de seguridad de Lync Server 2013
TOCTitle: Características clave de seguridad de Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56271352
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Características clave de seguridad de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 incluye varias características de seguridad, como la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración.

Este artículo ofrece información general de alto nivel sobre la seguridad de Lync Server 2013.

## Características clave de seguridad de Lync Server 2013

La seguridad es un concepto muy amplio que se integra en todas las características de Lync Server 2013, así como en las bases de datos, los servicios y el hardware que componen los ecosistemas de Lync. Este artículo destaca algunas características específicas de Lync Server 2013 que se han diseñado para aportar seguridad.

## Herramientas de planeación y diseño

Lync Server 2013 ofrece dos herramientas que facilitan las tareas de planeación y diseño y reducen el riesgo de configurar los componentes de Lync Server de un modo incorrecto.

  - **Herramienta de planeación de topologías** automatiza gran parte del proceso de diseño de las topologías. Los resultados pueden exportarse desde la Herramienta de planeación al Generador de topologías, herramienta que a su vez resulta necesaria para instalar los servidores que ejecutan Lync Server 2013.

  - **Generador de topologías** almacena toda la información de configuración en el Almacén de administración central.

Para más información sobre estas herramientas, consulte [Planeación de Lync Server 2013](lync-server-2013-planning.md).

## Almacén de administración central

En Lync Server 2013, los datos de configuración de servidores y servicios se encuentran integrados en el Almacén de administración central. Este almacén ofrece un sistema sólido y esquematizado de almacenamiento de los datos necesarios para definir, configurar, mantener, administrar, describir y trabajar con una implementación de Lync Server. También valida los datos para garantizar la coherencia de la configuración. Todos los cambios de esta configuración se realizan en el Almacén de administración central y se eliminan los problemas relacionados con errores de sincronización.

Las copias de solo lectura de los datos se replican a todos los servidores de la topología, incluidos los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. La replicación se administra desde un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red, y así se reducen los derechos y los permisos a los de un usuario ordinario en un equipo.

## Autenticación de servidor a servidor

Con el protocolo Open Authorization (OAuth) puede configurarse la autenticación de Lync Server 2013 entre servidores. Por ejemplo, Lync Server 2013 puede configurarse para realizar la autenticación con un servidor que ejecuta Exchange Server 2013. El protocolo OAuth permite activar la confianza entre los servidores de Lync y Exchange para integrar los productos sin ningún problema. Para más información, vea [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

## Administración basada en Windows PowerShell e interfaz de administración basada en web

Lync Server 2013 cuenta con una interfaz de administración muy eficaz integrada en la interfaz de la línea de comandos de Windows PowerShell, que incluye cmdlets para la administración de la seguridad. Las características de seguridad de Windows PowerShell se habilitan de forma predeterminada, de manera que los usuarios no pueden ejecutar scripts con demasiada facilidad o de forma involuntaria. Esto significa que los valores predeterminados de software se establecen automáticamente con el objetivo de maximizar la seguridad y reducir las vías de ataque. Para más información sobre la compatibilidad de la administración de Windows PowerShell y Lync Server 2013, vea [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Control de acceso basado en roles (RBAC)

El control de acceso basado en roles (RBAC) de Microsoft Lync Server 2013 permite delegar tareas administrativas y a la vez mantener altos estándares de seguridad. Con RBAC puede seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que su trabajo requiere. Lync Server 2013 incorpora las capacidades de crear nuevos roles y modificar roles existentes. Para más información, vea [Planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

## Traducción de direcciones de red (NAT)

Lync Server 2013 no es compatible con la traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero sí permite situar la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V tras un enrutador o firewall que realice este tipo de traducción para topologías de servidor perimetral consolidadas, tanto independientes como escaladas. No se puede usar NAT si se sitúan varios servidores perimetrales tras un equilibrador de carga de hardware. De ser varios los servidores perimetrales que usan NAT en sus interfaces externas, deberá aplicarse el equilibrio de carga del Sistema de nombres de dominio (DNS) que, a su vez, permite reducir el número de direcciones IP públicas por servidor perimetral en un grupo de servidores de este tipo. Para más información, vea [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).


> [!NOTE]
> Si una empresa se federa con otra que cuenta con una implementación de Microsoft Office Communications Server&nbsp;2007 y se requiere el uso de audio o vídeo entre ambas empresas, los requisitos de puertos serán los correspondientes a la versión más antigua de los servidores perimetrales que se encuentran implementados. Por ejemplo, los intervalos de puertos requeridos para esas versiones más antiguas deberán abrirse para ambas empresas hasta que el socio federado actualice sus servidores perimetrales a Lync Server&nbsp;2013. A partir de ese momento, podrán revisarse los requisitos en materia de puertos y reducirse conforme a la nueva configuración.



## Certificados simplificados para servidores perimetrales

El Asistente para implementar puede rellenar de forma automática los nombres del firmante (SN) y los nombres alternativos del firmante (SAN), para reducir así la posibilidad de especificar entradas que no resulten necesarias o puedan ser poco seguras.

## Ciclo de vida de desarrollo de seguridad de informática de confianza (SDL)

El diseño y el desarrollo de Lync Server 2013 se han realizado conforme al ciclo de vida de desarrollo de seguridad de informática de confianza de Microsoft (SDL) que se describe en <http://go.microsoft.com/fwlink/?linkid=68761>.

  - **De confianza por el diseño**   Para crear un sistema de comunicaciones unificadas más seguro, en primer lugar se diseñaron modelos de riesgos y se probaron las distintas características. Asimismo, Microsoft realiza pruebas al margen del comportamiento que se considera a la hora de efectuar el diseño, para buscar vulnerabilidades de seguridad derivadas de comportamientos inesperados del producto. Se han compilado varias mejoras relacionadas con la seguridad en los procesos y los procedimientos de codificación. Las herramientas en tiempo de compilación detectaron la saturación del búfer y otras posibles amenazas para la seguridad antes de comprobarse el código en el producto final. En cualquier caso, es imposible diseñar en función de todas las amenazas desconocidas en materia de seguridad. Ningún sistema puede garantizar una seguridad total. Ahora bien, dado que el desarrollo de los productos se basa en todo momento en los principios del diseño seguro, Lync Server 2013 incorpora las tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura.

  - **De confianza de forma predeterminada**   De forma predeterminada, las comunicaciones de red de Lync Server 2013 se encuentran cifradas. Todos los servidores usan la autenticación Kerberos y de certificados, la seguridad TLS, el protocolo de transporte seguro en tiempo real (SRTP) y otras técnicas de cifrado estándar del sector, incluido el Estándar de cifrado avanzado (AES) de 128 bits, y por ello se puede afirmar que prácticamente todos los datos de Lync Server se encuentran protegidos en la red. Asimismo, el control de acceso basado en roles permite implementar servidores que ejecutan Lync Server 2013 de manera que cada rol del servidor tan solo ejecuta los servicios que resultan apropiados (y únicamente dispone de los permisos relacionados con estos servicios).

  - **De confianza por la implementación**   Toda la documentación de Lync Server 2013 incluye recomendaciones de procedimientos y diversos aspectos que le ayudarán a determinar y configurar los niveles de seguridad óptimos para una implementación específica, y a evaluar los riesgos de seguridad a los que deberá enfrentarse si activa opciones distintas de las predeterminadas.

