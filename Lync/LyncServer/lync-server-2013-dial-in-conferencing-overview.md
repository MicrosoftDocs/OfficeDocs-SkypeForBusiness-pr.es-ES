---
title: Funciones de la conferencia de acceso telefónico local en Lync Server 2013
TOCTitle: Funciones de la conferencia de acceso telefónico local en Lync Server 2013
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48275597
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Funciones de la conferencia de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Si su organización tiene usuarios que necesitan asistir a conferencias locales de Lync Server 2013 nm-ocs-14-1st-legal-desc cuando no están en la oficina o no tienen acceso a un equipo, puede implementar la conferencia de acceso telefónico local para que puedan unirse a la conferencia utilizando un teléfono en la red telefónica conmutada (RTC).

La conferencia de acceso telefónico local es una característica opcional que puede configurar al implementar las conferencias de Lync Server 2013. Aunque la conferencia de acceso telefónico local usa algunos de los mismos componentes de Lync Server 2013 que usa la Telefonía IP empresarial, puede implementar la conferencia de acceso telefónico local aunque no implemente la Telefonía IP empresarial.


> [!NOTE]
> Si implementa la conferencia de acceso telefónico local, deberá implementarla en cada uno de los grupos de servidores en los que se implementen las conferencias de Lync Server 2013. No es necesario que asigne números de acceso en cada uno de los grupos de servidores, pero deberá implementar la característica de acceso telefónico local en todos ellos. Este requisito admite la característica de nombre registrado cuando un usuario llama a un número de acceso desde un grupo de servidores para unirse a una conferencia de Lync Server 2013 en un grupo de servidores diferente.



Las conferencias deben estar habilitadas para el acceso telefónico local en la directiva de reunión. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:

  - Un identificador de conferencia numérico que identifica la conferencia.

  - Uno o más números de acceso de RTC.

  - Un vínculo a una Página Configuración de conferencia de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un lugar para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como, por ejemplo, los controles de tono de marcado de frecuencia múltiple (DTMF).

Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Los usuarios de empresa tienen credenciales de Servicios de dominio de Active Directory y cuentas de Lync Server 2013 en la organización. Los usuarios anónimos no tienen credenciales de empresa en la organización. En el contexto de una conferencia de acceso telefónico local, un usuario de una organización asociada federada que usa la RTC para conectarse a una conferencia se considera usuario anónimo. A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.

Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local marcan uno de los números de acceso a la conferencia y, a continuación, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El Servidor front-end usa la combinación de la extensión o número de teléfono completo y el PIN para asignar únicamente usuarios de empresa a sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.


> [!NOTE]
> A los usuarios de empresa que usan el acceso telefónico local desde un teléfono IP de oficina, o bien desde Lync Server 2013 o Operador de Lync 2010, no se les pide su número de teléfono, ya que ya se les ha autenticado.



Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, deben marcar uno de los números de acceso a la conferencia y, a continuación, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.


> [!NOTE]
> Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia.



A la hora programada, el organizador de la reunión puede restringir el acceso a la reunión bloqueándola o cerrándola. En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen. Si prefieren no autenticarse o no lo hacen correctamente, se les transferirá a la sala de espera, donde esperarán hasta que el coordinador acepte o rechace su entrada, o bien hasta que se agote el tiempo de espera y sean desconectados. Los usuarios de acceso telefónico local escucharán música mientras esperan su admisión a la conferencia. Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) con las teclas del teléfono. Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida. Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde. Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.

Los participantes de acceso telefónico (es decir, los participantes que accedan o no desde el RTC) oirán anuncios personales durante la conferencia, como si han sido silenciados o se les ha dado la voz, si la reunión está siendo grabada o si hay alguien esperando en la sala de espera.


> [!NOTE]
> Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder mediante el marcado telefónico, no oirán anuncios personales.


