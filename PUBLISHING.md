# Publishing Guide

## Publishing to npm

### Prerequisites
1. npm account (create at https://www.npmjs.com/signup)
2. npm CLI installed (`npm --version`)
3. Logged in to npm (`npm login`)

### Steps

1. **Verify package.json**:
```bash
cd contentgenius
cat package.json
```

2. **Test package locally**:
```bash
npm pack
# This creates a .tgz file you can test
```

3. **Publish to npm**:
```bash
npm publish --access public
```

**Result**: Package available at https://www.npmjs.com/package/@epsimoai/contentgenius

### Installation (after publishing)
```bash
# Via npm
npm install -g @epsimoai/contentgenius

# Via Claude Code
claude code skill install @epsimoai/contentgenius
```

---

## Listing on skills.sh

### What is skills.sh?
skills.sh is the official Claude Code skill marketplace where users discover skills.

### Submission Process

1. **Ensure Prerequisites**:
   - ✅ Skill published to npm or GitHub
   - ✅ README.md with clear documentation
   - ✅ skill.json manifest file
   - ✅ Working skills/contentgenius/SKILL.md
   - ✅ Examples and usage guide

2. **Visit skills.sh**:
   - Go to https://skills.sh
   - Click "Submit Skill" or "Add Your Skill"

3. **Provide Information**:
   ```json
   {
     "name": "Content Genius",
     "package": "@epsimoai/contentgenius",
     "description": "Complete AI-powered content creation and proposal generation system",
     "repository": "https://github.com/epsimoai/contentgenius",
     "author": "Epsimo AI",
     "categories": ["productivity", "business", "content", "marketing"],
     "commands": ["contentgenius", "cgenius", "cg", "content"],
     "tags": [
       "content-creation",
       "proposals",
       "questionnaires",
       "marketing",
       "ai-generation"
     ]
   }
   ```

4. **Required Assets**:
   - Icon/Logo (optional but recommended)
   - Screenshots of usage
   - Video demo (optional)

5. **Submit for Review**:
   - Fill out submission form
   - Provide npm package link: `@epsimoai/contentgenius`
   - Or GitHub link: `epsimoai/contentgenius`
   - Wait for approval (usually 1-3 days)

### Skill Listing Information

**Title**: Content Genius - AI Content & Proposals

**Short Description**:
Generate professional content, proposals, and shareable client questionnaires with AI

**Long Description**:
Complete AI-powered content creation and proposal generation system for Claude Code. Generate emails, blog posts, social media content, commercial proposals, and PowerPoint presentations with simple commands. Create shareable questionnaire links for client intake forms that require no login. Includes a complete 3-stage proposal pipeline with market research integration.

**Key Features**:
- 🚀 AI content generation (email, blog, social, proposals, PPTX)
- 🔗 Shareable client questionnaires (no login required)
- 📊 Complete proposal pipeline with market research
- 🎨 Custom branding support
- ⚡ Async processing for long operations
- 📧 Email notifications
- 🔄 Auto-proposal generation

**Commands**:
- `/contentgenius email <topic>` - Generate professional emails
- `/contentgenius blog <topic>` - Create blog posts
- `/contentgenius social <message>` - Social media content
- `/contentgenius proposal <details>` - Generate proposals
- `/contentgenius pptx <title> <slides>` - Create presentations
- `/contentgenius questionnaire create <client>` - Shareable intake forms
- `/contentgenius proposal-pipeline <client>` - Complete automation

**Use Cases**:
- Marketing agencies creating proposals
- Consultants generating client content
- SaaS companies with lead qualification
- Content creators managing workflows
- Sales teams automating outreach

**Configuration Required**:
- CGENIUS_EPSIMO_TOKEN (required)
- CGENIUS_PROJECT_TOKEN (optional, for async)
- CGENIUS_API_BASE_URL (optional, defaults provided)

**Links**:
- npm: https://www.npmjs.com/package/@epsimoai/contentgenius
- GitHub: https://github.com/epsimoai/contentgenius
- Documentation: https://github.com/epsimoai/contentgenius#readme
- Issues: https://github.com/epsimoai/contentgenius/issues

---

## Alternative: Submit via GitHub Issue

If skills.sh has a GitHub repository for submissions:

1. Go to their GitHub repo (e.g., `github.com/claudecode/skills`)
2. Create new issue: "Add Content Genius skill"
3. Use this template:

```markdown
## Skill Submission

**Name**: Content Genius
**Package**: @epsimoai/contentgenius
**Repository**: https://github.com/epsimoai/contentgenius

### Description
Complete AI-powered content creation and proposal generation system with shareable client questionnaires.

### Features
- AI content generation (email, blog, social, proposals, PPTX)
- Shareable client questionnaires (no login required)
- Complete proposal pipeline with market research
- Custom branding support
- Async processing

### Categories
- Productivity
- Business
- Content
- Marketing

### Commands
- `/contentgenius email <topic>`
- `/contentgenius blog <topic>`
- `/contentgenius social <message>`
- `/contentgenius proposal <details>`
- `/contentgenius questionnaire create <client>`
- `/contentgenius proposal-pipeline <client>`

### Installation
```bash
claude code skill install @epsimoai/contentgenius
```

### Links
- npm: https://www.npmjs.com/package/@epsimoai/contentgenius
- GitHub: https://github.com/epsimoai/contentgenius
- README: https://github.com/epsimoai/contentgenius#readme
```

---

## Post-Publishing Checklist

After publishing:

- [ ] Test installation: `npm install -g @epsimoai/contentgenius`
- [ ] Verify npm page: https://www.npmjs.com/package/@epsimoai/contentgenius
- [ ] Test Claude Code install: `claude code skill install @epsimoai/contentgenius`
- [ ] Submit to skills.sh
- [ ] Share on social media
- [ ] Update documentation with npm install instructions
- [ ] Monitor for issues/feedback

---

## Versioning

Follow semantic versioning (semver):

- **Patch** (1.0.x): Bug fixes
- **Minor** (1.x.0): New features, backward compatible
- **Major** (x.0.0): Breaking changes

### Publishing Updates

```bash
# Patch release
npm version patch
npm publish

# Minor release
npm version minor
npm publish

# Major release
npm version major
npm publish
```

---

## Troubleshooting

### Error: Package name already exists
- Use scoped package: `@yourscope/contentgenius`
- Already using scoped package: `@epsimoai/contentgenius` ✅

### Error: Not logged in
```bash
npm login
# Enter username, password, email
```

### Error: 403 Forbidden
```bash
# Ensure public access
npm publish --access public
```

### Error: Skills.sh submission not appearing
- Wait 1-3 days for review
- Check spam folder for notification email
- Contact skills.sh support

---

## Maintenance

### Regular Updates
- Monitor issues on GitHub
- Respond to user feedback
- Update dependencies
- Add new features based on requests
- Improve documentation

### Community
- Respond to issues within 48 hours
- Accept pull requests
- Update changelog
- Thank contributors

---

## Support

Need help publishing?

- npm docs: https://docs.npmjs.com/cli/v8/commands/npm-publish
- Claude Code docs: https://code.claude.com/docs/en/skills
- skills.sh: https://skills.sh
- GitHub Issues: https://github.com/epsimoai/contentgenius/issues
