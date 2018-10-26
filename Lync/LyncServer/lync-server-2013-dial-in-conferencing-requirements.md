---
title: Planeación de las conferencias de acceso telefónico local en Lync Server 2013
TOCTitle: Planeación de las conferencias de acceso telefónico local en Lync Server 2013
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48276129
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de las conferencias de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Antes de iniciar el proceso de implementación del Lync Server 2013 nm-ocs-14-1st-legal-desc, debe planear lo siguiente:

  - La configuración que usará para conectarse a la red telefónica conmutada (RTC)

  - La estrategia que empleará para asignar regiones de conferencia de acceso telefónico local a números de acceso telefónico

  - La estrategia que empleará para crear directorios de conferencia

## Planeación de la conectividad con RTC de acceso telefónico

Las conferencias de acceso telefónico local requieren como mínimo un Servidor de mediación y una puerta de enlace RTC.

Puede implementar un Servidor de mediación en un sitio central o en un sitio de sucursal. En un sitio central, puede instalar un Servidor de mediación en un Grupo de servidores front-end o en un Servidor Standard Edition, o bien puede implementarlo en un servidor o en un grupo de servidores independiente. En un sitio de sucursal, puede implementar un Servidor de mediación en un servidor independiente o como componente de la Aplicación de sucursal con funciones de supervivencia.

Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal. En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la Aplicación de sucursal con funciones de supervivencia.


> [!NOTE]
> Las conferencias de acceso telefónico local no usan el desvío de medios porque los Servidor de conferencia A/V no lo admiten.



Para obtener más información sobre cómo planear su configuración para Servidor de mediación y puertas de enlace RTC para conferencias de acceso telefónico local, consulte [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación sobre planeamiento.

## Planeación de las regiones de conferencia de acceso telefónico local

Durante la configuración de acceso telefónico, se crean planes de marcado y números de acceso a conferencias de acceso telefónico local. Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos de un número de teléfono y convierten el número de teléfono al formato E.164 estándar para el enrutamiento de llamadas. Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.

Cada número de acceso a conferencias de acceso telefónico local debe estar asociado por lo menos con un plan de marcado. Las regiones de conferencia de acceso telefónico local asocian un número de acceso a conferencias de acceso telefónico local con sus planes de marcado. Al definir un plan de marcado, se especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado. Cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado pertinentes.

Al crear un plan de marcado, se especifica el ámbito del mismo: ámbito de usuario, ámbito de grupo de servidores o ámbito de sitio. A cada usuario se asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario. Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede. Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores. Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio. Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global.

Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes deben aplicarse a las regiones de conferencia de acceso telefónico local:

  - Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.

  - Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.

  - Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.

  - De forma predeterminada, todos los números de acceso telefónico local de la región se incluyen en la invitación a la reunión.

  - Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente. El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación. (Cuando los usuarios utilizan Outlook para programar una reunión, el usuario usa el Complemento para conferencia en línea para Lync 2013 para cambiar la región).

  - Las regiones deben asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.

  - Puede configurar el orden en que los números de acceso de una región aparecen en la Página Configuración de conferencia de acceso telefónico local (y, por tanto, el orden en que aparecen en la invitación a la conferencia) mediante los cmdlets del Shell de administración de Lync Server.

  - Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.

## Planeación de los directorios de conferencia

Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia mediante Lync 2013 y el identificador de conferencia numérico que un participante de una conferencia de acceso telefónico local usa para unirse a la conferencia. El formato del identificador de conferencia es el siguiente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los Id. de conferencia, por lo general, se mantendrán cortos. Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.

## Vea también

#### Conceptos

[Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

