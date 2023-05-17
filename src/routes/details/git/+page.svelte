<script>
        import GitLogo from '$lib/img/git-logo.png';
</script>

<div class="site">
        <section id="intro">
                <h1>Git - Versionskontrolle für Softwareentwicklung</h1>
                <p>
                        Git ist ein verteiltes Versionskontrollsystem, das für die Verwaltung von Änderungen an Code, Textdokumenten, Bildern und anderen Dateien verwendet wird. Es
                        wurde von Linus Torvalds im Jahr 2005 für die Entwicklung des Linux-Kernels erstellt und wird heute von Millionen von Entwicklern weltweit genutzt.
                </p>
                <img src={GitLogo} alt="Git logo" />
        </section>
        <section id="content">
                <h2>Wie Git funktioniert</h2>
                <p>
                        Git funktioniert, indem es eine Kopie des Repositorys (also des Verzeichnisses mit allen Dateien) auf Ihrem lokalen Computer speichert. Jeder Entwickler
                        kann dann Änderungen an Dateien vornehmen, die er/sie dann committen kann. Diese Änderungen werden dann als "Commit" in der lokalen Kopie des Repositorys
                        gespeichert.
                </p>
                <p>
                        Wenn ein Entwickler fertig ist und die Änderungen mit dem Hauptrepository teilen möchte, kann er/sie einen "Push" durchführen, um die Änderungen auf den
                        gemeinsamen Server zu übertragen. Andere Entwickler können dann die Änderungen durch "Pull" auf ihren lokalen Computer herunterladen.
                </p>
                <h2>Warum Git so wichtig ist</h2>
                <p>
                        Git ist ein wichtiger Bestandteil der modernen Softwareentwicklung, da es Entwicklern ermöglicht, Änderungen an Code effektiv und effizient zu verwalten und
                        zu teilen. Es ermöglicht auch eine einfachere Zusammenarbeit zwischen Entwicklern, indem es ermöglicht, Änderungen zu verfolgen und Konflikte zu lösen.
                </p>
                <p>
                        Darüber hinaus kann Git auch zur Verwaltung von Projekten, Dokumentationen und anderen Arten von Dateien verwendet werden. Es ist eine vielseitige und
                        leistungsstarke Software, die für jedes Unternehmen oder jede Organisation, die Software entwickelt oder Date
                </p>
        </section>
</div>

<style>
        .site {
                display: grid;
                grid-template-columns: 1fr 2fr;
                grid-gap: 20px;
                padding: 20px;
        }

        section {
                background-color: #fff;
                padding: 20px;
        }

        @media (max-width: 600px) {
                /* Mobile-Ansicht */
                .site {
                        grid-template-rows: auto 1fr auto;
                        grid-template-columns: 1fr;
                }
        }
</style>
