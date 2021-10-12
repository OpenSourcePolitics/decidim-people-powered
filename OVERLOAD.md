# List of overloaded files for specific needs in this repository

## Remove version from proposal presenter (line 129)
 - **app/views/decidim/proposals/proposals/show.html.erb**
```ruby
    <%= resource_version(proposal_presenter, versions_path: proposal_versions_path(@proposal)) %
```
