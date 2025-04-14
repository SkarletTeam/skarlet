---
layout: default
title: Homepage
description: Skarlet Corp. Managed IT and Cyber Security Services in Dixie County Florida
---

<!-- Header-->
<header class="bg-dark py-5">
    <div class="container px-5">
        <div class="row gx-5 align-items-center justify-content-center">
            <div class="col-lg-8 col-xl-7 col-xxl-6">
                <div class="my-5 text-center text-xl-start">
                    <h1 class="display-5 fw-bolder text-white mb-2">Skarlet Corp.</h1>
					<p class="display-5 fw-bolder text-white mb-2"><strong>IT Solutions You Can Rely On</strong></p>
                    <p class="lead fw-normal text-white mb-4">Skarlet Corp delivers reliable, affordable IT solutions for SMBs in Dixie County, FL. With 16+ years of experience, we keep your systems running smoothly and secure against cyber threats.</p>
                    <div class="d-grid gap-3 d-sm-flex justify-content-sm-center justify-content-xl-start">
                        <a class="btn btn-primary btn-lg px-4 me-sm-3" href="#features">Get Started</a>
                        <a class="btn btn-outline-primary btn-lg px-4" href="#services">Learn More</a>
                    </div>
                </div>
            </div>
            <div class="col-xl-5 col-xxl-6 d-none d-xl-block text-center"><img class="img-fluid rounded-3 my-5" src="/img/desk.webp" alt="Skarlet Corp. IT Solutions" /></div>
        </div>
    </div>
</header>
<!-- Features section-->
<section class="py-5" id="features">
    <div class="container px-5 my-5">
        <div class="row gx-5">
            <div class="col-lg-4 mb-5 mb-lg-0"><h2 class="fw-bolder mb-0">Comprehensive IT Support Tailored to Your Business Needs</h2></div>
            <div class="col-lg-8">
                <div class="row gx-5 row-cols-1 row-cols-md-2">
                    <div class="col mb-5 h-100">
                        <div class="feature badge-gradient  text-white rounded-3 mb-3"><i class="bi bi-collection"></i></div>
                        <h2 class="h5">Remote Monitoring & Maintenance</h2>
                        <p class="mb-0">With our remote monitoring services, we constantly keep an eye on your systems to detect and address issues before they disrupt your business. Our proactive approach minimizes downtime, ensuring your business stays up and running 24/7.</p>
                    </div>
                    <div class="col mb-5 h-100">
                        <div class="feature badge-gradient  text-white rounded-3 mb-3"><i class="bi bi-building"></i></div>
                        <h2 class="h5">Patch Management</h2>
                        <p class="mb-0">Keeping software and systems updated is crucial for security. We manage and apply patches regularly, so you don’t have to worry about potential vulnerabilities.</p>
                    </div>
                    <div class="col mb-5 mb-md-0 h-100">
                        <div class="feature badge-gradient  text-white rounded-3 mb-3"><i class="bi bi-toggles2"></i></div>
                        <h2 class="h5">Security & Compliance Assistance</h2>
                        <p class="mb-0">As cybersecurity threats continue to evolve, businesses are under increasing pressure to stay compliant with regulations. We help you meet industry standards and secure your data against breaches, malware, and phishing attacks.</p>
                    </div>
                    <div class="col h-100">
                        <div class="feature badge-gradient  text-white rounded-3 mb-3"><i class="bi bi-toggles2"></i></div>
                        <h2 class="h5">Business Suite & Email Backup Services</h2>
                        <p class="mb-0">Your data is the lifeblood of your business. Our cloud backup services ensure that your critical files, including emails and accounting data like QuickBooks, are always safe and easily recoverable in the event of an emergency.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Testimonial section-->
<section>
<div class="py-2">
    <div class="container px-2 my-2">
        <div class="row gx-5 justify-content-center">
					{% include reviews.html %}
		</div>
    </div>
</div>
</section>
<!-- Services section-->
<section class="py-5">
    <div class="container px-5 my-5" id="services">
        <div class="row gx-5 justify-content-center">
            <div class="col-lg-8 col-xl-6">
                <div class="text-center" id="Services">
                    <h2 class="fw-bolder">Services</h2>
                    <br>
                </div>
            </div>
        </div>
        <div class="row gx-5">
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/voip.webp" alt="Managed VoIP" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient rounded-pill mb-2">VoIP</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/managed_voip"><h5 class="card-title mb-3">Managed VoIP & Conference Room Equipment Installs</h5></a>
                        <p class="card-text mb-0">Enhance call quality, access cutting-edge VoIP features, and resolve issues quickly with our Managed VoIP service.</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/backups.webp" alt="Business Suite and Email Backups" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">Backups</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/backup_services"><h5 class="card-title mb-3">Business Suite and Email Backups</h5></a>
                        <p class="card-text mb-0">Comprehensive Backup Solutions for Business Suite & Email</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/password.webp" alt="Password Managers & MFA" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">Cyber Security</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/cyber_security_services"><h5 class="card-title mb-3">Password Managers and Multi-factor Authentication</h5></a>
                        <p class="card-text mb-0">Secure Your Accounts with Password Management & Multi-Factor Authentication</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row gx-5">
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/techy_girl.webp" alt="Detection and Response" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">Cyber Security</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/cyber_security_services"><h5 class="card-title mb-3">Endpoint Detection & Response (EDR) and Managed Detection & Response (MDR)</h5></a>
                        <p class="card-text mb-0">Advanced Threat Protection with Endpoint & Managed Detection and Response (EDR/MDR)</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/microsoft.webp" alt="Microsoft 365 Solutions" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">IT Servies</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/it_services"><h5 class="card-title mb-3">Microsoft 365 Solutions</h5></a>
                        <p class="card-text mb-0">Optimize productivity, enhance security, and streamline collaboration with our Microsoft services, including Email, Azure, and Teams.</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/virus.webp" alt="Anti-Virus" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">Cyber Security</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/cyber_security_services"><h5 class="card-title mb-3">Business Grade Anti-Virus (AV)</h5></a>
                        <p class="card-text mb-0">Robust Business-Grade Antivirus for Maximum Protection</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row gx-5">
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/field-engineer.webp" alt="Remote Monitoring & Management" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">IT Services</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/it_services"><h5 class="card-title mb-3">Remote Monitoring & Management (RMM)</h5></a>
                        <p class="card-text mb-0">Proactive Remote Monitoring & Management for Your IT Infrastructure</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/remote_worker.webp" alt="Remote Work Solutions" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">IT Services</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/it_services"><h5 class="card-title mb-3">Remote Work Solutions</h5></a>
                        <p class="card-text mb-0">Secure, Seamless, and Efficient Remote Work Solutions</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-4 mb-5">
                <div class="card h-100 shadow border-0">
                    <img class="card-img-top" src="/img/remote_support.webp" alt="Remote Support" />
                    <div class="card-body p-4">
                        <div class="badge badge-gradient  rounded-pill mb-2">IT Services</div>
                        <a class="text-decoration-none link-dark stretched-link" href="/services/it_services"><h5 class="card-title mb-3">Unlimited Remote Support & Contracted On-Site Support</h5></a>
                        <p class="card-text mb-0">Reliable IT Support: Unlimited Remote Support & Contracted On-Site Services</p>
                    </div>
                    <div class="card-footer p-4 pt-0 bg-transparent border-top-0">
                        <div class="d-flex align-items-end justify-content-between">
                            <div class="d-flex align-items-center">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
	</div>
</section>