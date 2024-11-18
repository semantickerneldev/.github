---
title: Tips Listing
---

import React from 'react';
import { useDocusaurusContext } from '@docusaurus/core';
import Layout from '@theme/Layout';

const TipsList = () => {
  const { siteConfig } = useDocusaurusContext();
  const tips = siteConfig.customFields.tips;

  const sortedTips = tips.sort((a, b) => a.tip_number - b.tip_number);

  return (
    <Layout title="Tips Listing">
      <div className="container">
        <h1>Tips Listing</h1>
        <ul>
          {sortedTips.map((tip) => (
            <li key={tip.tip_number}>
              <a href={`/docs/tips/tip${tip.tip_number}`}>{`Tip ${tip.tip_number} - ${tip.title}`}</a>
            </li>
          ))}
        </ul>
      </div>
    </Layout>
  );
};

export default TipsList;
