
**Yes, Firebase has a free tier** called the **Spark Plan**.

It requires **no credit card** or payment information to get started, making it popular for hobby projects, prototyping, and learning.

### What is Included for Free (Spark Plan)

- **Firebase Hosting**: Includes **10 GB of storage** and a generous data transfer limit per day. It also supports custom domains with free SSL certificates.
    
- **Authentication**: Free for up to 50,000 Monthly Active Users (MAUs) for standard login methods (email/password, Google sign-in, etc.).
    
- **Cloud Firestore (Database)**: 1 GB of total stored data, 50,000 reads per day, and 20,000 writes per day.
    
- **Cloud Storage**: 5 GB of storage for files like images and user uploads.
    

### The Catch to Keep in Mind

- **Hard Limits**: If your app grows and crosses any of those daily or monthly free thresholds on the Spark plan, your service will temporarily pause or block traffic until the next day rather than charging you.
    
- **The Blaze Plan Option**: To scale past the free limits automatically without getting blocked, developers switch to the **Blaze (Pay-as-you-go) plan**. Even on the Blaze plan, you still get all of the free quotas mentioned above—you only pay for what you use _above_ those free limits.

Here are the direct links to the Google tools we've discussed, along with a few other major Google platforms for building, hosting, and creating:

### The Tools We Covered

- **Firebase**: [firebase.google.com](https://firebase.google.com/) _(Backend services, databases, authentication, and hosting)_
    
- **Google Sites**: [sites.google.com](https://sites.google.com/) _(No-code, browser-based drag-and-drop website builder)_
    
- **Google Cloud (GCP)**: [cloud.google.com](https://cloud.google.com/) _(Enterprise cloud computing, serverless tools like Cloud Run, and virtual machines)_
    

### Other Major Google Platforms for Building & Hosting

- **Google AI Studio**: [aistudio.google.com](https://aistudio.google.com/)
    
    - _What it is_: A fast, developer-focused environment to prototype and build generative AI applications using Google's Gemini models with a generous free tier.
        
- **Google Play Console / Android Studio**: [developer.android.com](https://developer.android.com/)
    
    - _What it is_: Google's official platform and IDE for building, testing, and publishing native Android mobile apps.
        
- **Google App Engine**: [cloud.google.com/appengine](https://cloud.google.com/appengine)
    
    - _What it is_: A fully managed serverless platform built into Google Cloud that lets you deploy web apps in languages like Python, Java, Node.js, and PHP without managing servers.
Yes, you can change your **GitHub account username**, but there are important things you need to know before doing it.

### How to Change Your GitHub Username:

1. Log into **GitHub.com**.
    
2. Click your **profile picture** in the upper-right corner, then click **Settings**.
    
3. In the left sidebar, click **Account**.
    
4. Look for the **Change username** section and click the button.
    
5. Read the warnings, click **I understand, let's change my username**, type your new username, and confirm.
    

### Important Things That Happen When You Change It:

- **Repository URLs**: GitHub automatically sets up redirects from your old repository links to your new ones. However, to avoid future issues, you should update the remote URL on your local computer's terminal for any active projects:
    
    Bash
    
    ```
    git remote set-url origin https://github.com/your-new-username/your-repo-name.git
    ```
    
- **Old Username Becomes Available**: Once you change your username, your old username is immediately released. Anyone else on GitHub can claim it, and **GitHub will not redirect your old profile page**.
    
- **Links & Badges**: Links to your personal profile page or `@mentions` in issues/pull requests from other users will break and will not automatically redirect.

Finding a clean, tech-focused handle that bridges your name (`raulcontreraso`) with something generic or IT-oriented is a great move for a professional developer profile.

Here are a few structured naming formulas you can use, along with ideas inspired by your current handle:

### 1. Initials + Tech / IT Focus

- `dev_rcontreras`
    
- `rc_devops`
    
- `rcontreras_code`
    
- `it_rc`
    

### 2. Role or Industry-Based (Clean & Professional)

- `devops_raco` (similar to your idea)
    
- `code_raco`
    
- `cloud_rc`
    
- `sys_raco`
    

### 3. Abstract / Modern Developer Handles

- `raco_bytes`
    
- `rc_syntax`
    
- `null_raco`
    
- `bit_raco` (keeping a nod to your old `-bit` suffix)
    

### How to Change Your GitHub Username (Quick Reminder)

Once you pick a new name:

1. Go to GitHub **Settings** > **Account** > **Change username**.
    
2. Update your local machine's remote URL in your project terminal so it points to the new path:
    
    Bash
    
    ```
    git remote set-url origin https://github.com/your-new-username/your-repo-name.git
    ```
    

Do you lean more toward keeping a piece of your initials (like `rc`) or going completely abstract with something like `devops_raco`?