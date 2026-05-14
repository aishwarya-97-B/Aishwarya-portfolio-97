
```react
import React, { useState } from 'react';
import { 
  Settings, 
  TrendingUp, 
  ShieldCheck, 
  ChevronRight, 
  Box, 
  Mail, 
  Linkedin, 
  BookOpen, 
  ExternalLink, 
  Copy, 
  Check,
  MapPin
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('overview');
  const [copiedId, setCopiedId] = useState(null);

  const copyToClipboard = (url, id) => {
    navigator.clipboard.writeText(url);
    setCopiedId(id);
    setTimeout(() => setCopiedId(null), 2000);
  };

  const profile = {
    name: "Aishwarya Balakrishnan",
    title: "Strategic Operations & Lifecycle Lead",
    location: "United Arab Emirates",
    email: "aishwarya397@yahoo.com",
    linkedin: "https://www.linkedin.com/in/aishwarya-b-262605185",
    summary: "Strategic professional with 5+ years of cross-functional experience optimizing operational execution, vendor management, and lifecycle engagement. Specialized in building the 'infrastructure of engagement'—combining complex supply chain management with data-driven communication strategies to drive retention in high-growth ecosystems.",
    skillClusters: [
      {
        title: "Operational Strategy",
        icon: <Settings className="text-indigo-600" />,
        skills: ["Supply Chain Logistics", "Vendor Onboarding & Management", "SOP Development", "Regulatory & Legal Alignment"]
      },
      {
        title: "Lifecycle & Retention",
        icon: <TrendingUp className="text-emerald-600" />,
        skills: ["Segmented Communication", "Retention Data Analysis", "Value Proposition Design", "NPS Growth"]
      },
      {
        title: "Project Governance",
        icon: <ShieldCheck className="text-purple-600" />,
        skills: ["End-to-End Project Ownership", "Cross-functional Leadership", "Research & Thought Leadership", "Stakeholder Management"]
      }
    ]
  };

  const blogs = [
    {
      id: "blog-1",
      title: "Moonlighting: Fading Commitment vs. Innovation",
      desc: "An analytical look at the operational risks and potential innovative benefits of the moonlighting trend.",
      url: "https://www.scalentsolutions.com/blog/moonlighting---fading-employee-commitment-vs-innovation",
      tag: "Workforce Strategy"
    },
    {
      id: "blog-2",
      title: "The Strategic Value of Boomerang Employees",
      desc: "Evaluating the cost-effectiveness and cultural impact of rehiring former talent.",
      url: "https://www.scalentsolutions.com/blog/the-new-trend-of-boomerang-employees-effective-or-not-should-you-hire-or-not",
      tag: "Recruitment Ops"
    },
    {
      id: "blog-3",
      title: "AI in Automated Sourcing & Job Matching",
      desc: "Exploring how AI-driven frameworks optimize the efficiency of matching talent to operational needs.",
      url: "https://www.scalentsolutions.com/blog/how-ai-can-help-in-automated-sourcing-job-matching",
      tag: "Tech Integration"
    },
    {
      id: "blog-4",
      title: "Post-COVID Recruitment Challenges",
      desc: "Synthesizing the landscape of talent acquisition hurdles in a hybrid world.",
      url: "https://www.scalentsolutions.com/blog/recruitment-challenges-faced-by-recruiters-and-candidates-post-covid",
      tag: "Industry Analysis"
    }
  ];

  const caseStudies = [
    {
      title: "UAE-Wide Supply Chain & Engagement Infrastructure",
      subtitle: "The 'Summer Together' Program",
      metrics: "20,000+ Riders | 20+ Partners",
      challenge: "Coordinating a massive logistics and engagement initiative across all 7 Emirates during peak high-attrition summer months.",
      solution: "Engineered a robust supply chain for refreshment kits and vetted production vendors. Strategically onboarded 20+ restaurant partners nationwide as distribution hubs and aligned with legal for UAE-wide regulatory compliance.",
      impact: ["Secured 100% distribution coverage across UAE", "Maintained fleet stability during peak heat months", "Optimized vendor costs through strategic production selection"],
      tags: ["Supply Chain", "Vendor Ops", "Legal Alignment"]
    },
    {
      title: "Communication SOP & Engagement Optimization",
      subtitle: "Fleet-Wide Communication Strategy",
      metrics: "18% Read-Rate Growth (57% → 75%)",
      challenge: "Inefficient communication absorption and lack of control over messaging priorities led to information gaps and reduced campaign effectiveness.",
      solution: "Implemented a segmented targeting framework and revised the global SOP for communication timelines. Established strict content control and prioritization protocols.",
      impact: ["Achieved 75% read rate MoM", "Enhanced campaign participation across all segments", "Reduced information fatigue and increased SOP compliance"],
      tags: ["Governance", "Data Analytics", "Strategy"]
    }
  ];

  return (
    <div className="min-h-screen bg-[#FFFDF5] text-slate-900 font-sans">
      <nav className="sticky top-0 bg-[#FFFDF5]/90 backdrop-blur-md border-b border-orange-100 z-50">
        <div className="max-w-6xl mx-auto px-6 h-16 flex items-center justify-between">
          <div className="flex items-center gap-2">
            <div className="w-8 h-8 bg-indigo-600 rounded-lg flex items-center justify-center text-white font-bold text-lg">AB</div>
            <p className="font-bold text-sm">Aishwarya B.</p>
          </div>
          <div className="flex gap-1 bg-orange-50/50 p-1 rounded-full border border-orange-100">
            {['overview', 'projects'].map((tab) => (
              <button 
                key={tab}
                onClick={() => setActiveTab(tab)} 
                className={`px-4 py-1.5 rounded-full text-[10px] font-bold uppercase tracking-wider transition-all ${activeTab === tab ? 'bg-white text-indigo-600 shadow-sm' : 'text-slate-500 hover:text-slate-800'}`}
              >
                {tab}
              </button>
            ))}
          </div>
        </div>
      </nav>

      <header className="pt-16 pb-24 max-w-6xl mx-auto px-6">
        <div className="max-w-3xl">
          <div className="inline-flex items-center gap-2 bg-indigo-50 border border-indigo-100 px-3 py-1 rounded-full text-indigo-600 text-xs font-bold mb-6 uppercase tracking-wider">
            Operational Strategy & Execution
          </div>
          <h1 className="text-4xl md:text-6xl font-black text-slate-900 tracking-tight mb-6">
            Bridging <span className="text-indigo-600">Strategy</span> and <span className="text-blue-500">Execution</span>.
          </h1>
          <p className="text-lg text-slate-600 leading-relaxed mb-10">{profile.summary}</p>
          <div className="flex flex-wrap gap-4">
            <a href={`mailto:${profile.email}`} className="bg-slate-900 text-white px-6 py-3 rounded-xl font-bold flex items-center gap-2 hover:bg-slate-800 transition-all shadow-lg">
              <Mail size={18} /> Contact Me
            </a>
            <a href={profile.linkedin} target="_blank" rel="noopener noreferrer" className="flex items-center gap-2 px-6 py-3 bg-white border border-slate-200 rounded-xl font-bold text-slate-600 hover:border-indigo-500 transition-all">
              <Linkedin size={18} className="text-indigo-500" /> LinkedIn
            </a>
          </div>
        </div>
      </header>

      <main className="max-w-6xl mx-auto px-6 pb-24">
        {activeTab === 'overview' && (
          <div className="space-y-20">
            <div className="grid md:grid-cols-3 gap-6">
              {profile.skillClusters.map((cluster, i) => (
                <div key={i} className="bg-white/80 p-8 rounded-3xl border border-orange-100 shadow-sm backdrop-blur-sm">
                  <div className="w-12 h-12 bg-orange-50 rounded-xl flex items-center justify-center mb-6">
                    {cluster.icon}
                  </div>
                  <h4 className="font-bold text-lg mb-4">{cluster.title}</h4>
                  <ul className="space-y-3">
                    {cluster.skills.map(skill => (
                      <li key={skill} className="flex items-center gap-2 text-sm text-slate-500 font-medium">
                        <div className="w-1.5 h-1.5 bg-indigo-200 rounded-full" /> {skill}
                      </li>
                    ))}
                  </ul>
                </div>
              ))}
            </div>

            <section>
              <h3 className="text-2xl font-bold flex items-center gap-2 mb-8">
                <BookOpen className="text-indigo-600" /> Thought Leadership & Insights
              </h3>
              <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-4">
                {blogs.map((blog, idx) => (
                  <div key={idx} className="group bg-white/90 p-6 rounded-2xl border border-orange-100 shadow-sm hover:border-indigo-200 hover:shadow-md transition-all flex flex-col justify-between backdrop-blur-sm">
                    <div>
                      <div className="flex justify-between items-start mb-3">
                        <span className="text-[9px] font-black tracking-widest uppercase text-indigo-500 bg-indigo-50 px-2 py-0.5 rounded inline-block">{blog.tag}</span>
                        <button onClick={() => copyToClipboard(blog.url, blog.id)} className="text-slate-300 hover:text-indigo-500 transition-colors p-1">
                          {copiedId === blog.id ? <Check size={14} /> : <Copy size={14} />}
                        </button>
                      </div>
                      <h4 className="font-bold text-sm text-slate-900 group-hover:text-indigo-600 transition-colors mb-2 leading-snug">{blog.title}</h4>
                      <p className="text-[11px] text-slate-500 leading-relaxed mb-4 line-clamp-2">{blog.desc}</p>
                    </div>
                    <a href={blog.url} target="_blank" rel="noopener noreferrer" className="flex items-center text-[10px] font-bold text-slate-400 hover:text-indigo-500 transition-colors">
                      OPEN ARTICLE <ExternalLink size={12} className="ml-1" />
                    </a>
                  </div>
                ))}
              </div>
            </section>

            <section className="bg-slate-900 rounded-[2.5rem] p-10 text-white">
              <div className="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                <div>
                  <div className="text-4xl font-black text-indigo-400 mb-1">18%</div>
                  <p className="text-slate-400 text-[10px] font-bold uppercase tracking-widest leading-tight">Comm. Efficiency Growth</p>
                </div>
                <div>
                  <div className="text-4xl font-black text-emerald-400 mb-1">20K+</div>
                  <p className="text-slate-400 text-[10px] font-bold uppercase tracking-widest leading-tight">Deliver Rider Impact</p>
                </div>
                <div>
                  <div className="text-4xl font-black text-blue-400 mb-1">10+</div>
                  <p className="text-slate-400 text-[10px] font-bold uppercase tracking-widest leading-tight">Strategic Partnerships</p>
                </div>
                <div>
                  <div className="text-4xl font-black text-purple-400 mb-1">5+</div>
                  <p className="text-slate-400 text-[10px] font-bold uppercase tracking-widest leading-tight">Years Experience</p>
                </div>
              </div>
            </section>
          </div>
        )}

        {activeTab === 'projects' && (
          <div className="space-y-10">
            {caseStudies.map((project, idx) => (
              <div key={idx} className="bg-white rounded-3xl border border-orange-100 overflow-hidden shadow-sm hover:border-indigo-200 transition-all">
                <div className="flex flex-col lg:flex-row">
                  <div className="lg:w-1/3 bg-orange-50/30 p-10 border-b lg:border-b-0 lg:border-r border-orange-100">
                    <span className="text-[10px] font-black tracking-widest uppercase text-slate-400 mb-2 block">Case Study</span>
                    <h3 className="text-2xl font-black text-slate-900 leading-tight mb-2">{project.title}</h3>
                    <p className="text-indigo-600 font-bold text-sm mb-6">{project.subtitle}</p>
                    <div className="bg-white p-4 rounded-xl border border-orange-100">
                      <p className="text-[10px] font-bold text-slate-400 uppercase mb-1">Key Impact</p>
                      <p className="text-lg font-black text-slate-800">{project.metrics}</p>
                    </div>
                  </div>
                  <div className="lg:w-2/3 p-10">
                    <div className="space-y-6">
                      <p className="text-slate-600 text-sm leading-relaxed">{project.challenge}</p>
                      <div className="bg-indigo-50/50 p-5 rounded-2xl">
                        <h4 className="text-[10px] font-black uppercase text-indigo-400 tracking-widest mb-3">Outcomes</h4>
                        <ul className="space-y-2">
                          {project.impact.map((imp, i) => (
                            <li key={i} className="text-[13px] font-bold text-slate-700 flex items-start gap-2">
                              <Box size={14} className="mt-0.5 text-indigo-500 flex-shrink-0" /> {imp}
                            </li>
                          ))}
                        </ul>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            ))}
          </div>
        )}
      </main>

      <footer className="bg-white border-t border-orange-100 py-16 px-6 text-center">
        <h2 className="text-3xl font-black mb-4 italic text-slate-900">Let's connect.</h2>
        <div className="flex justify-center flex-wrap gap-4 mt-8">
          <a href={`mailto:${profile.email}`} className="bg-slate-900 text-white px-8 py-3 rounded-xl font-bold flex items-center gap-2 hover:bg-slate-800 transition-all shadow-lg">
            <Mail size={18} /> Email
          </a>
          <a href={profile.linkedin} target="_blank" rel="noopener noreferrer" className="border border-slate-200 bg-white px-8 py-3 rounded-xl font-bold flex items-center gap-2 hover:border-indigo-500 hover:text-indigo-600 transition-all shadow-sm">
            <Linkedin size={18} /> LinkedIn
          </a>
        </div>
      </footer>
    </div>
  );
};

export default App;


```
