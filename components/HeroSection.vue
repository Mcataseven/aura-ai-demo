<template>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="container relative z-10">
      <div class="center" style="max-width: 800px; margin: 0 auto;">
        <h1>Your CRM, Reinvented.</h1>
        <p>Experience a faster, smarter way to work. Aura AI combines your entire workflow into a single, intelligent
          platform powered by AI automation and seamless simplicity.</p>
        <div class="hero-cta">
          <NuxtLink to="/register" class="btn btn-lg btn-primary">Get Started for Free</NuxtLink>
          <NuxtLink to="/features" class="btn btn-lg btn-outline">Explore Features</NuxtLink>
        </div>
      </div>

      <!-- AI Chat Mockup -->
      <div class="mt-20" style="max-width: 960px; margin: 80px auto 0;">
        <div class="card rounded shadow-1">
          <!-- User Query -->
          <div class="row">
            <div class="avatar">
              <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/>
              </svg>
            </div>
            <div style="flex:1;">
              <div class="bubble">Show me my top 5 qualified leads from last week.</div>
            </div>
          </div>

          <!-- AI Response -->
          <div class="row" style="margin-top: 16px;">
            <div class="avatar primary">
              <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/>
                <path d="M5 3v4"/><path d="M19 17v4"/><path d="M3 5h4"/><path d="M17 19h4"/>
              </svg>
            </div>
            <div style="flex:1;">
              <div class="bubble bubble-muted">I found your top 3 qualified leads from last week. Here they are:</div>

              <!-- Leads -->
              <div class="grid grid-3" style="margin-top:12px;">
                <!-- Lead 1 -->
                <div class="lead-card fade-in d0">
                  <div class="lead-head">
                    <div>
                      <h4 class="lead-name">Sarah Chen</h4>
                      <div class="lead-meta">
                        <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18Z"/><path d="M6 12H4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h2"/><path d="M18 9h2a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2h-2"/><path d="M10 6h4"/><path d="M10 10h4"/><path d="M10 14h4"/><path d="M10 18h4"/>
                        </svg>
                        <span>TechVision Inc.</span>
                      </div>
                    </div>
                    <div class="lead-score">
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/>
                      </svg>
                      94
                    </div>
                  </div>
                  <div class="lead-info">
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/>
                      </svg>
                      <span style="margin-left:6px;">sarah.chen@techvision.io</span>
                    </div>
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.63A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                      </svg>
                      <span style="margin-left:6px;">+1 (555) 123-4567</span>
                    </div>
                  </div>
                  <div class="lead-badge">
                    <span class="badge-primary">Hot Lead</span>
                  </div>
                </div>

                <!-- Lead 2 -->
                <div class="lead-card fade-in d1">
                  <div class="lead-head">
                    <div>
                      <h4 class="lead-name">Marcus Rodriguez</h4>
                      <div class="lead-meta">
                        <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18Z"/><path d="M6 12H4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h2"/><path d="M18 9h2a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2h-2"/><path d="M10 6h4"/><path d="M10 10h4"/><path d="M10 14h4"/><path d="M10 18h4"/>
                        </svg>
                        <span>CloudScale Systems</span>
                      </div>
                    </div>
                    <div class="lead-score">
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/>
                      </svg>
                      89
                    </div>
                  </div>
                  <div class="lead-info">
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/>
                      </svg>
                      <span style="margin-left:6px;">m.rodriguez@cloudscale.com</span>
                    </div>
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.63A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                      </svg>
                      <span style="margin-left:6px;">+1 (555) 234-5678</span>
                    </div>
                  </div>
                  <div class="lead-badge">
                    <span class="badge-primary">Qualified</span>
                  </div>
                </div>

                <!-- Lead 3 -->
                <div class="lead-card fade-in d2">
                  <div class="lead-head">
                    <div>
                      <h4 class="lead-name">Emily Watson</h4>
                      <div class="lead-meta">
                        <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18Z"/><path d="M6 12H4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h2"/><path d="M18 9h2a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2h-2"/><path d="M10 6h4"/><path d="M10 10h4"/><path d="M10 14h4"/><path d="M10 18h4"/>
                        </svg>
                        <span>DataFlow Analytics</span>
                      </div>
                    </div>
                    <div class="lead-score">
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/>
                      </svg>
                      87
                    </div>
                  </div>
                  <div class="lead-info">
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/>
                      </svg>
                      <span style="margin-left:6px;">e.watson@dataflow.ai</span>
                    </div>
                    <div>
                      <svg class="icon-sm" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.63A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                      </svg>
                      <span style="margin-left:6px;">+1 (555) 345-6789</span>
                    </div>
                  </div>
                  <div class="lead-badge">
                    <span class="badge-primary">Qualified</span>
                  </div>
                </div>

              </div><!-- grid -->
            </div>
          </div><!-- row -->
        </div><!-- card -->
      </div><!-- mockup -->
    </div>
  </section>


</template>